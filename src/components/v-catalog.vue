<script>
import vCatalogItem from './v-catalog-item.vue'

export default {
  name: 'v-catalog',
  components: {
    vCatalogItem
  },
  props: {},
  data() {
    return {
      products:[
          {
            image: `1.jpg`,
            name: "T-shirt 1",
            price: 100,
            article: "T1",
            available: true
          },
          {
            image: `2.jpg`,
            name: "T-shirt 2",
            price: 300,
            article: "T2",
            available: true
          },
          {
            image: `3.jpg`,
            name: "T-shirt 3",
            price: 200,
            article: "T3",
            available: true
          },
          {
            image: `4.jpg`,
            name: "T-shirt 4",
            price: 500,
            article: "T4",
            available: false
          }
      ]
    }
  },
  computed: {},
  methods:{
    showChild(data){
      console.log(data)
    }
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
    @sendArticle="showChild"/>
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
