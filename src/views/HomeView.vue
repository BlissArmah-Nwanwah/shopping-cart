<template>
  <div class="home">
  <div class="propuct-cards-container"> 
    <ProductDescriptionDrawer :product="product" :active="active.product_drawer" />
 <ProductSummaryCard 
 v-for="product in items" :key="product.id" :product="product" v-on:view-product="viewProduct($event)" />
  </div>
  </div>
</template>

<script>
// @ is an alias to /src
import items from '../data/items.js'
import ProductSummaryCard from '../components/products/ProductSummaryCard.vue'
import ProductDescriptionDrawer from '../components/products/ProductDescriptionDrawer.vue'

export default {
  name: 'HomeView',
  components: {    
    ProductSummaryCard,
    ProductDescriptionDrawer,
  },
  data(){
    return{
      items: items,
      product: null,
      active : {
        product_drawer : true
      }
    }
  },
  methods: {
    viewProduct(product){
      this.product = product
      console.log(this.product);
    }
  },
}
</script>

<style lang="scss">
.propuct-cards-container{
display: flex;
flex-wrap:wrap ;
justify-content: center;

}
</style>