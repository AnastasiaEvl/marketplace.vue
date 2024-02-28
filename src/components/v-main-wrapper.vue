<template>
  <div class="v-main-wrapper">{{ title }}</div>
  <v-catalog/>
  <v-cart v-if="cart.length"/>
</template>
<script>
import vCatalog from './v-catalog.vue'
import vCart from './v-cart.vue'
import {mapGetters} from "vuex";

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
  computed: {
    ...mapGetters(['cart'])
  },
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
