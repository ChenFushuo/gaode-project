<template>
  <div class="index_container">
    <div class="map_warp">
      <MapContainer></MapContainer>
    </div>
  </div>
</template>

<script>
import MapContainer from "@/components/MapContainer/MapContainer.vue";

export default {
  components: {
    MapContainer
  }
}
</script>

<style lang="scss" scoped>
.index_container {
  width: 100%;
  height: 100%;
  position: relative;

  .map_warp {
    width: 100%;
    height: 100%;
  }
}
</style>