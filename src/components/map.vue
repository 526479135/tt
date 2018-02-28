<template>
    <div id="map-container"></div>
</template>

<style rel="stylesheet/scss" lang="scss" scoped>
#map-container {
  position: absolute;
  width: 100%;
  height: 100%;
}
</style>

<script>
import AMap from "AMap";
export default {
  name: 'mapGd',
  mounted () {
    this.init()
  },
  methods:{
    init(){
      const map = new AMap.Map('map-container', {
        zoom: 12
      })
      let markers = [];
      for(var i=0;i<points.length;i+=1){
        markers.push(new AMap.Marker({
          position:points[i]['lnglat'],
          content: '<div style="background-color: hsla(180, 100%, 50%, 0.7); height: 24px; width: 24px; border: 1px solid hsl(180, 100%, 40%); border-radius: 12px; box-shadow: hsl(180, 100%, 50%) 0px 0px 1px;"></div>',
          offset: new AMap.Pixel(-15,-15)
        }))
      }
  	  new AMap.MarkerClusterer(map, markers,{gridSize:80});
    }
  }
}
</script>