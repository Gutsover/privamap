<template>
  <q-page class="flex">
    <q-card class="my-map">
      <l-map :zoom="zoom" :center="center" style="height: 100%; width: 100%">
        <l-tile-layer :url="url"></l-tile-layer>
        <l-marker :lat-lng="markerLatLng"></l-marker>
        <l-geo-json
          v-for="shape in shapes"
          :key="shape.id"
          :geojson="shape.geometry"
          @click="getInfo"
        ></l-geo-json>
      </l-map>
    </q-card>
    <information-panel></information-panel>
  </q-page>
</template>

<script>
import { LMap, LTileLayer, LMarker, LGeoJson } from "vue2-leaflet";
import L from "leaflet";
import "leaflet/dist/leaflet.css";
import { Icon } from "leaflet";
import InformationPanel from "components/InformationPanel.vue";
import Shapes from "src/assets/shapes.json";

delete Icon.Default.prototype._getIconUrl;
Icon.Default.mergeOptions({
  iconRetinaUrl: require("leaflet/dist/images/marker-icon-2x.png"),
  iconUrl: require("leaflet/dist/images/marker-icon.png"),
  shadowUrl: require("leaflet/dist/images/marker-shadow.png")
});

export default {
  name: "PageIndex",

  components: {
    LMap,
    LTileLayer,
    LMarker,
    LGeoJson,
    InformationPanel
  },

  data() {
    return {
      zoom: 15,
      center: [50.64093925317058, 3.0445486307144165],
      url: "https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png",
      markerLatLng: [50.64093925317058, 3.0445486307144165],
      geojson: null,
      shapes: Shapes
    };
  },

  methods: {
    getInfo() {
      console.log(this.shapes.keys);
    },
    getLocation() {
      navigator.geolocation.getCurrentPosition(
        position => {
          this.long = position.coords.longitude;
          this.lat = position.coords.latitude;
          this.markerLatLng = [this.lat, this.long];
          this.center = [this.lat, this.long];
        },
        err => {
          console.log(err);
        }
      );
    }
  },
  mounted() {
    // this.getLocation();
  }
};
</script>

<style lang="sass">
.q-page
  @media (max-width: 970px)
    display: block
.my-map
  width: 70%
  @media (max-width: 970px)
    width: 100%
    min-height: 60vh

</style>
