<template>
  <q-card bordered class="bg-grey-3 my-card" >
    <q-card-section>
      <div class="text-h6">{{ title }}</div>
      <div class="text-subtitle2">{{ shortTitle }}</div>
      {{ description }}
    </q-card-section>

    <q-separator white inset />
    <q-card-section>
      <span>Coordonnées: {{ coordinate }}</span>
      <q-separator white inset />
      <img src="https://cdn.quasar.dev/img/parallax2.jpg" />
    </q-card-section>
  </q-card>
</template>

<script>
import Elements from "src/assets/elements.json";
import Shapes from "src/assets/shapes.json";

export default {
  name: "InformationPanel",
  data() {
    return {
      title: "Nom de l'élément",
      shortTitle: "Dénomination courte",
      description:
        "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore",
      coordinate: "3.0445486307144165, 50.64093925317058"
    };
  }
};
</script>

<style lang="sass">
.q-card
    width: 30%
    margin: 0 0 0 0
    @media (max-width: 970px)
        width: 100%
        height: 300px
        overflow: auto
        padding: 0
img
    margin: 15px
    height: 150px
    width: 150px

</style>