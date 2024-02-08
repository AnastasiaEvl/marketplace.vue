<script>

export default {
  name:'v-catalog-item',
  props: {
    product_data: {
      type:Object,
      default(){
        return{}
      }
    }
  },
  methods: {
    sendDataToParent(){
      this.$emit('sendArticle',this.product_data.article)
    }
  }
}
</script>

<template>
  <div class="v-catalog-item">
    <img :src='/images/+product_data.image' alt="img" class="v-catalog-item__img">
    <p class="v-catalog-item_name">{{product_data.name}}</p>
    <p class="v-catalog-item_price">Price: {{product_data.price}} $</p>
    <button
        @click="sendDataToParent"
        class="v-catalog-item__add_to_cart_btn btn"
    >Add to cart</button>
  </div>

</template>

<style lang="scss">
.v-catalog-item {
  flex-basis: 25%;
  box-shadow: 0 0 8px 0 #e0e0e0;
  padding: $padding*2;
  margin-bottom: $margin*2;

  &__img{
    width: auto;
    height: 120px;
  }
}
</style>
