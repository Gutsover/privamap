<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>


        <q-toolbar-title>
          Test Technique
        </q-toolbar-title>

        <q-btn v-for="type in types" :key="type.id" label= {{ type.name }}/>




      </q-toolbar>
    </q-header>



    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
  import { Quasar, QBtn } from 'quasar'
  import axios from "axios"

export default {
  name: 'MainLayout',
  components: {
    QBtn
  },
  data() {
    return {
      types: []
    }
  },
  methods: {
    getType() {

      this.$axios.get('types.json')
          .then((response) => {
            this.types = response.data
              console.log('types:',this.types)
          })
          .catch((err) => {
              console.log('Erreur:', err)
          })
    },

  },
  created() {
      this.getType()
    }

}
</script>
