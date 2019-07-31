<template>
  <div id="map"></div>
</template>

<script>
import mapboxgl from "mapbox-gl";

export default {
  name: "MapboxMap",
  data() {
    return {
      center: null,
      zoom: null
    };
  },
  mounted() {
    // create the map after the component is mounted
    this.createMap();
  },
  methods: {
    createMap() {
      // instantiate map
      this.map = new mapboxgl.Map({
        accessToken:
          "pk.eyJ1IjoiYmZyaWVkbHkiLCJhIjoiY2p4bHd1OXdpMGFycDN0bzFiNWR4d2VyNyJ9.3hQjvgyoPoCuRx-Hqr_BFQ",
        container: "map",
        style: "mapbox://styles/mapbox/streets-v11",
        minzoom: 5,
        center: [-93.1247, 44.9323], // St. Paul
        zoom: 10.5,
        hash: true // sets url's hash to #zoom/lat/lng
      });

      // set mapbox event listeners to update Vue component data
      this.map.on("move", () => {
        this.center = this.map.getCenter();
      });
      this.map.on("zoom", () => {
        this.zoom = this.map.getZoom();
      });
    }
  }
};
</script>

<style scoped>
#map {
  height: 400px;
  width: 100%;
}
</style>
