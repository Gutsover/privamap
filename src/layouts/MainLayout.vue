<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>
        <q-toolbar-title>
          Test Technique
        </q-toolbar-title>
        <button-type></button-type>
      </q-toolbar>
    </q-header>
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import ButtonType from "components/ButtonType.vue";

export default {
  name: "MainLayout",
  components: { ButtonType }
  // data () {
  //   return {
  //     leftDrawerOpen: false
  //   }
  // }
};
</script>