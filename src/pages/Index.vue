<template>
  <q-page padding class="flex">
    <q-card style="flex:1">
      <l-map :zoom="zoom" :center="center" style="height: 100%; width: 70%" >
        <l-tile-layer :url="url" ></l-tile-layer>
        <l-marker :lat-lng="markerLatLng" ></l-marker>
      </l-map>

    </q-card>
  </q-page>
</template>

<script>
import { LMap, LTileLayer, LMarker } from 'vue2-leaflet'
import L from 'leaflet'
import 'leaflet/dist/leaflet.css'
import { Icon } from 'leaflet'

delete Icon.Default.prototype._getIconUrl;
Icon.Default.mergeOptions({
  iconRetinaUrl: require('leaflet/dist/images/marker-icon-2x.png'),
  iconUrl: require('leaflet/dist/images/marker-icon.png'),
  shadowUrl: require('leaflet/dist/images/marker-shadow.png'),
});

  export default {

    name: 'PageIndex',

    components: {
      LMap,
      LTileLayer,
      LMarker
    },

    data() {
      return {
        zoom: 15,
        center: [0, 0],
        url: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
        markerLatLng: [0, 0]
      };
    },

    methods: {
      getLocation () {
        navigator.geolocation.getCurrentPosition(
          (position) => {
            this.long= position.coords.longitude
            this.lat= position.coords.latitude
            this.markerLatLng = [this.lat, this.long]
            this.center = [this.lat, this.long]
          },
          (err) => {
            console.log(err);
          }
        )
      }
    },
    mounted () {
        this.getLocation()
    }
  }
</script>


