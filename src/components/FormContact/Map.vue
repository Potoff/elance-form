<template>
    <ol-map :loadTilesWhileAnimating="true" :loadTilesWhileInteracting="true" style="height:400px"
        class="w-full mt-10 xl:mt-0"
        @click="getCoordinate"
        >

        <ol-view ref="view" :center="center" :rotation="rotation" :zoom="zoom" :projection="projection" />

        <ol-tile-layer>
            <ol-source-osm />
        </ol-tile-layer>
    </ol-map>
</template>

<script setup>
function getCoordinate(e){
    e.stopPropagation();
    const coordinates = e.frameState
    console.log(coordinates)
}

</script>