<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar class="bg-cyan-9">
        <q-toolbar-title>
          Test Technique
        </q-toolbar-title>
        <search-bar></search-bar>
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
import SearchBar from 'src/components/SearchBar.vue';

export default {
  name: "MainLayout",
  components: { ButtonType, SearchBar }
  // data () {
  //   return {
  //     leftDrawerOpen: false
  //   }
  // }
};
</script>
