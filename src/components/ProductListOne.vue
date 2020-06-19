<template>
    <div id="product-list-one">
        <h2>Product List One</h2>
        <ul>
            <li v-for="product in saleProducts" v-bind:key="product">
                <span class="name">{{product.name}}</span>
                <span class="name">{{product.price}}</span>
            </li>
        </ul>
        <button v-on:click="reducePrice(4)">Reduce Price</button>
    </div>
</template>

<script>
import {mapActions} from 'vuex';
import {mapGetters} from 'vuex';

export default {
    // props: ['products'],
    // data() {
    //     return {
           
    //     };
    // }
    computed: {
        products(){
            return this.$store.state.products;
        },
        // saleProducts(){
        //     return this.$store.getters.saleProducts;
        // }
        ...mapGetters([
            'saleProducts'
        ])
    },
    methods: {
        // reducePrice: function(amount){
        //     // this.$store.commit('reducePrice');
        //     this.$store.dispatch('reducePrice', amount);
        // }
        ...mapActions([
            'reducePrice' 
        ])
    },
};
</script>

<style>

</style>
