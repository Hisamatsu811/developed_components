<template>
  <AccordionMenu />
</template>

<script lang="ts">
import Vue from 'vue'
import AccordionMenu from '~/components/AccordionMenu.vue'

export default Vue.extend({
  components: {
    AccordionMenu
  }
})
</script>

<style lang="scss" scoped>
html {
  background: lightgrey;
}
</style>
