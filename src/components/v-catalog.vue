<script>
import vCatalogItem from './v-catalog-item.vue'
import {mapActions, mapGetters} from "vuex";

export default {
  name: 'v-catalog',
  components: {
    vCatalogItem
  },
  props: {},
  data() {
    return {
    }
  },
  computed: {
    ...mapGetters(['products'])
  },
  methods:{
    ...mapActions([
        'GET_PRODUCTS_FROM_API',
        'ADD_TO_CART'
    ]),
    addToCart(data){
     this.ADD_TO_CART(data)
    }
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API().then((response)=>{
      if(response.data){
        console.log('Data get')
      }
    })
  }
}

</script>

<template>
  <div class="v-catalog">
    <h1>Catalog</h1>
    <div class="v-catalog_list">
    <v-catalog-item v-for="product in products"
    :key="product.article"
    :product_data="product"
    @addToCart="addToCart"/>
  </div>
  </div>


</template>

<style lang="scss">
.v-catalog {
  text-align: center;
  &_list {
    display: grid;
    grid-template-columns: repeat(2,1fr);
    justify-content: space-between;
    gap: 2rem;
    margin: 1rem 5rem;
    align-items: center;
  }
}


</style>
