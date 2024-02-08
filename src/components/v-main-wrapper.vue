<template>
  <div class="v-main-wrapper">{{ title }}</div>
  <v-catalog/>
  <v-cart/>
</template>
<script>
import vCatalog from './v-catalog.vue'
import vCart from './v-cart.vue'
export default {
  name: 'v-main-wrapper',
  components: {
    vCatalog,
    vCart
  },
  props: {},
  data() {
    return {
      title: ''
    }
  },
  computed: {},
  methods: {},
  watch: {},
}
</script>

<style>
.v-main-wrapper {
  max-width: 900px;
  margin: 0 auto;
}
</style>
