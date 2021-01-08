
<template>
    <q-input bottom-slots v-model="text" label="Ex : 1 place Privamap, Lille, France" maxlength="150" clearable>
        <template v-slot:before>
          <q-icon name="place" />
        </template>
      </q-input>
</template>

<script>
export default {
    name: "SearchBar",

    data () {
        return {
        text: ''
        }
    }
}
</script>

<style lang="sass">
.q-field:active
    color: #eeeeee
</style>