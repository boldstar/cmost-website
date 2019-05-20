<template>
    <div class="gmap">
        <div class="content-row gmap-header">
            <img src="../../static/img/logo.png" alt="logo" class="gmap-logo">
            <h2 class="gmap-title">Our Location</h2>
        </div>
        <GmapMap
        :center="{lat:29.9244067, lng:-94.0175638}"
        :zoom="14"
        map-type-id="terrain"
        style="width: 400px; height: 400px"
        >
        <GmapMarker
            :key="index"
            :position="{lat:29.9244067, lng:-94.0175638}"
            :clickable="true"
            :draggable="true"
        />
        </GmapMap>
    </div>
</template>

<script>
export default {
name: 'Map'
}
</script>

<style>
.gmap {
    width: 400px;
}
.gmap-header {
    margin-bottom: 15px;
}

.gmap-title {
    margin-bottom: 0;
    align-self: center;
}

.gmap-logo {
    width: auto;
    height: 50px;
    margin-bottom: 10px;
}
</style>
