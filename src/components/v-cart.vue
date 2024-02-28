<script>
import vCartItem from './v-cart-item.vue'

export default {
  name:'v-cart',
  components:{
    vCartItem
  },
  props:{},
  data(){
    return{}
  },
  computed:{},
}

</script>

<template>
<div class="v-cart">
  <v-cart-item/>
</div>
</template>

<style scoped>

</style>
