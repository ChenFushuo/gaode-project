<template>
  <div id="container"></div>
</template>

<script>
import AMapLoader from '@amap/amap-jsapi-loader'

window._AMapSecurityConfig = {
  securityJsCode: 'f223606be120ea0f9be5edfd5bc47d2a'
}

export default {
  data() {
    return {
      map: null
    }
  },
  mounted() {
    this.initMap()
  },
  methods: {
    initMap() {
      AMapLoader.load({
        key: "8c797ac73a90390272e6fd5702ac151f",             // 申请好的Web端开发者Key，首次调用 load 时必填
        version: "2.0",      // 指定要加载的 JSAPI 的版本，缺省时默认为 1.4.15
        plugins: ['AMap.ToolBar', 'AMap.Scale', 'AMap.HawkEye', 'AMap.MapType', 'AMap.Geolocation'], // 需要使用的的插件列表，如比例尺'AMap.Scale'等
      }).then((AMap) => {
        this.map = new AMap.Map("container", {  //设置地图容器id
          viewMode: "3D",    //是否为3D地图模式
          zoom: 10,         //初始化地图级别
          center: [121.473667, 31.230525], //初始化地图中心点位置
        })
        this.map.addControl(new AMap.Scale())
        this.map.addControl(new AMap.ToolBar())
        this.map.addControl(new AMap.HawkEye())
        this.map.addControl(new AMap.MapType())
        this.map.addControl(new AMap.Geolocation())
      }).catch(e => {
        console.log(e);
      })
    },
  },
}
</script>

<style lang="scss" scoped>
#container {
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
}
</style>