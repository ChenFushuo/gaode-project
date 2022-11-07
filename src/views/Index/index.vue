<template>
  <div class="index_container">
    <div class="search_wrap">
      <Search></Search>
    </div>
    <div class="map_wrap">
      <MapContainer></MapContainer>
    </div>
  </div>
</template>

<script>
import MapContainer from "@/components/MapContainer/MapContainer.vue";
import Search from "@/components/Search/Search.vue";

export default {
  components: {
    MapContainer,
    Search
  }
}
</script>

<style lang="scss" scoped>
.index_container {
  width: 100%;
  height: 100%;
  position: relative;

  .map_wrap {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 60%;
    height: 60%;
  }

  .search_wrap {
    position: absolute;
    top: 10%;
    left: 10%;
    height: 60px;
    width: 400px;
  }

}
</style>