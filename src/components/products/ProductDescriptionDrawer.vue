<template>
    <div class="drawer-background" :class="{show: active}" @click="$emit('close-product-drawer')" />       

    <div class="drawer" :class="{show: active}">
    <div class="drawer-close" @click="$emit('close-product-drawer')">
        X
    </div>

    <div v-if="product" class="product-details">
        <h3 class="text-center">{{ product.name }}</h3>
        <p class="description">{{ product.description }}</p>
        <h3 class="text-center">${{ product.price.toFixed(2) }}</h3>

        <div class="card-total" v-if="product_total">
            <h3>In Cart</h3>
            <h4>{{ product_total }}</h4>
        </div>

        <div class="button-container">
            <button class="remove">Remove</button>
            <button class="add">Add</button>
        </div>
    </div>
    </div>
</template>


<script>
export default{
    props: ['product', 'active'],
    computed:{
        product_total(){
            return 56.00
        }
    }
}
</script>





<style lang="scss">
 .drawer-background{
    width: 100%;
    height: 100vh;
    position: fixed;
    left: 0;
    top:0;
    background: rgba( 124,124,124, 0.55 );
    z-index: 100;
    display: none;
    transition: display .5s;

    &.show{
        display: block;
    }
 }
 .drawer{
    width: 95vw;
    height: 100vh;
    background: white;
    position: fixed;
    top: 0;
    left: -105vw;
    padding: 15px;
    transition: left .5s;
    z-index: 101;
    overflow-y: scroll;

    &.show{
        left: 0;
    } 
 }


 
</style>