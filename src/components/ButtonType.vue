<template>
  <div class="button-type q-pa-md">
    <q-btn-dropdown color="cyan-9" label="Types">
      <q-list>
        <q-item
          v-for="type in types"
          :key="type.id"
          clickable
          v-close-popup
          @click="onItemClick"
        >
          <q-item-section>
            <q-item-label>{{ type.name }}</q-item-label>
          </q-item-section>
        </q-item>
      </q-list>
    </q-btn-dropdown>
  </div>
</template>

<script>
import { QBtn } from "quasar";
import Types from "src/assets/types.json";

export default {
  name: "ButtonType",
  components: {
    QBtn
  },
  data() {
    return {
      types: Types
    };
  },
  methods: {
    onItemClick() {
      // console.log('Clicked on an Item')
    }
  }
};
</script>

<style lang="sass">
.q-btn__wrapper:before
  box-shadow: none
  
</style>
