<template>
  <!--<l-map ref="map" :zoom="zoom" :center="center" @ready="onMapReady()">
    <l-tile-layer :url="url"></l-tile-layer>
  </l-map>-->
  <PlaygroundModal :playground="playground" />
</template>

<script setup>
import "leaflet/dist/leaflet.css";
import { LMap, LTileLayer } from "@vue-leaflet/vue-leaflet";

import PlaygroundModal from "./components/PlaygroundModal.vue";

export default {
  name: "App",
  components: {
    PlaygroundModal,
    // LMap,
    // LTileLayer,
  },

  /*   mounted() {
    this.$nextTick(() => {
      console.log(this.$refs.map.leafletObject);
    });
  }, */

  data() {
    return {
      url: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      attribution:
        '&copy; <a target="_blank" href="http://osm.org/copyright">OpenStreetMap</a> contributors',
      map: null,
      zoom: 15,
      center: [47.82591, 9.64404],
      playground: {
        title: "Spielplatz Schacherbuckel",
        accessibility: true,
        subtitles: ["Spielplatz", "Grasoberfläche"],
        playgroundgear: [
          {
            title: "Rutsche mit einer Welle",
            details: ["Mindestalter: 3"],
            cardicon: "slide",
          },
          {
            title: "Schaukel",
            details: ["Babyschaukel: Nein", "Anzahl: 2"],
            cardicon: "swing",
          },
          {
            title: "Sandkasten",
            details: [""],
            cardicon: "sandpit",
          },
          {
            title: "Klettergerüst",
            details: [],
            cardicon: "slide",
          },
          {
            title: "Babyschaukel",
            details: ["Babyschaukel: Nein", "Anzahl: 2"],
            cardicon: "slide",
          },
          {
            title: "Riesenschaukel",
            details: ["Babyschaukel: Nein", "Anzahl: 2"],
            cardicon: "swing",
          },
          {
            title: "Tischtennisplatte",
            details: ["Babyschaukel: Nein", "Anzahl: 2"],
            cardicon: "slide",
          },
        ],
      },
    };
  },

  /*   methods: {
    onMapReady(mapObject) {
      this.$nextTick(() => {
        const map = this.$refs.map.leafletObject;
        console.log("map: ", map);
      });
    },
  }, */
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

main {
  width: 100%;
  height: 600px;
  background-color: #2c3e50;
}

.centered-card {
  position: absolute;
  bottom: 0;
}
</style>
