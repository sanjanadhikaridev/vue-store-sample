<template>
    <div id="product-list-two">
        <h2>Product List Two</h2>
        <li v-for="product in saleProducts" v-bind:key="product">
            <span class="name">{{product.name}}</span>
            <span class="name">{{product.price}}</span>
        </li>
    </div>
</template>

<script>
export default {
    // props: ['products'],
    // data() {
    //     return {
    //     };
    // }
    computed: {
        products() {
            return this.$store.state.products;
        },
        saleProducts(){
            return this.$store.getters.saleProducts;
        }
    }
};
</script>

<style>

</style>
