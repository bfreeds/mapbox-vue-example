<template>
  <div id="app">
    <h1 class="title">Mapbox Map</h1>
    <MapboxMap />
  </div>
</template>

<script>
import MapboxMap from "./components/MapboxMap.vue";

export default {
  name: "app",
  components: {
    MapboxMap
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
