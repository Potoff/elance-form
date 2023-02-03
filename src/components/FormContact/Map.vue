<template>
    <ol-map :loadTilesWhileAnimating="true" :loadTilesWhileInteracting="true" style="height:400px"
        class="w-full mt-10 xl:mt-0" @click="getCoordinate">

        <ol-view ref="view" :center="center" :rotation="rotation" :zoom="zoom" :projection="projection" />

        <ol-tile-layer>
            <ol-source-osm />
        </ol-tile-layer>

        <ol-vector-layer>
            <ol-source-vector ref="vectors">
                <ol-interaction-draw @drawstart="drawstart" :type="drawType">
                </ol-interaction-draw>
            </ol-source-vector>

            <ol-style>
                <ol-style-icon :src="markerIcon" :scale="0.05"></ol-style-icon>
            </ol-style>
        </ol-vector-layer>


    </ol-map>
</template>



<script setup>
import { ref } from "vue";
import markerIcon from "../icons/Marker.svg"

const center = ref([2, 46.7])
const projection = ref('EPSG:4326')
const zoom = ref(6)
const rotation = ref(0)
const adress = ref('')

const markers = ref(null);
const drawType = ref("Point")

const drawedMarker = ref()
const vectors = ref(null);

const drawstart = (event) => {
    vectors.value.source.removeFeature(drawedMarker.value);
    drawedMarker.value = event.feature;
    console.log(vectors.value.source)
}

let emit = defineEmits(['click'])

function getCoordinate(e) {
    e.preventDefault();
    e.stopPropagation();
    let lat = e.target.pixelToCoordinateTransform_[5].toFixed(4)
    let long = e.target.pixelToCoordinateTransform_[4].toFixed(4)
    let api_key = 'ab6d70467aed4746bb66cf3c7fcb3717'
    fetch(`https://api.geoapify.com/v1/geocode/reverse?lat=${lat}&lon=${long}&format=json&apiKey=${api_key}`)
        .then((res) => res.json())
        .then((json) => {
            adress.value = json.results[0].formatted
            emit('click', adress.value)
        })
}


let api_key = 'ab6d70467aed4746bb66cf3c7fcb3717'

</script>

<style>
.overlay-content {
    background: #efefef;
    box-shadow: 0 5px 10px rgb(2 2 2 / 20%);
    padding: 10px 20px;
    font-size: 16px;
}
</style>