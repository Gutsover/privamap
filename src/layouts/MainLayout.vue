<template>
  <q-layout view="lHh Lpr lFf">
    <q-header elevated>
      <q-toolbar>


        <q-toolbar-title>
          Test Technique
        </q-toolbar-title>

        <q-btn-group push>
          <q-btn push label="First" />
          <q-btn push label="Second" />
          <q-btn push label="Third" />
        </q-btn-group>



      </q-toolbar>
    </q-header>



    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
  import { Quasar, QBtnGroup } from 'quasar'
  import axios from "axios"

  let customType = require('assets/types.json')

export default {
  name: 'MainLayout',
  components: {
    QBtnGroup
  }

}
</script>
