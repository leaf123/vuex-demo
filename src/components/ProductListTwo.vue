<template>
  <div class="ProductListTwo">
      <h2>Product List Two</h2>
      <ul>
        <li v-for="product in saleProducts" :key="product.value">
            <span class="name">{{product.name}}</span>
            <span class="price">${{product.price}}</span>
        </li>
      </ul>
  </div>
</template>

<script>
// import { mapState } from 'vuex'
import {mapGetters} from 'vuex'
import {mapActions} from 'vuex'
export default {
    computed:{
        // products(){
        //     return this.$store.state.products;
        // },
        // saleProducts(){
        //     return this.$store.getters.saleProducts;
        // }
         ...mapGetters([
            'products',
            'saleProducts'
        ])
    },
    methods:{
       /* reducePrice:function(amount){
            // this.$store.state.products.forEach(product =>{
            //     product.price -= 1;
            // })
           // this.$store.commit('reducePrice')
            this.$store.dispatch('reducePrice',amount);
        }*/
        // ...mapActions([
        //     'reducePrice'
        // ])
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .ProductListTwo{
    background: #D1E4FF;
    box-shadow: 1px 2px 3px rgba(0,0,0,0.2);
    margin-bottom: 30px;
    padding: 10px 20px;
    }
    .ProductListTwo ul{
        padding: 0;
        list-style-type: none;
    }
    .ProductListTwo li{
        margin-right: 10px;
        margin-top: 10px;
        padding: 20px;
        background: rgba(255,255,255,0.7);
    }
    .price{
        font-weight: bold;
        color: #860CE8;
        display: block;
    }
</style>
