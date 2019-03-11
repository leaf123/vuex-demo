<template>
  <div class="ProductListOne">
      <h2>Product List One</h2>
      <ul>
        <li v-for="product in saleProducts" :key="product.value">
            <span>{{diss_data}}</span>
            <span class="name">{{product.name}}</span>
            <span class="price">${{product.price}}</span>
        </li>
      </ul>
      <button @click="reducePrice(4)">商品降价16666</button>
  </div>
</template>
<script>
import {mapGetters} from 'vuex'
import {mapActions} from 'vuex'
export default {
//   props:["products"],
    data () {
        return {
            diss_data:''
        }
    },
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
        ...mapActions([
            'reducePrice'
        ])
    },
    created(){
        // fetch
        // fetch("/apis/api2.php/api/v1/get_top",{
        // method:"get",
        // headers:{
        //     "Content-type":"application/json"
        //     // token:"f4c902c9ae5a2a9d8f84868ad064e706"
        // },
        // // body:JSON.stringify({username:"henry",password:"321321"})
        // })
        // .then(result => {
        // console.log(result)
        // return result.json()
        // })
        // .then(data => {
        // console.log(data.data.top[0])
        // this.diss_data=data.data.top[0]
        // })

    // axios
    this.$axios.get("/apis/api2.php/api/v1/get_top")
        .then(data => {
          console.log(data.data.data.top[0])
          this.diss_data=data.data.data.top[0]
        })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .ProductListOne{
    background: #FFF8B1;
    box-shadow: 1px 2px 3px rgba(0,0,0,0.2);
    margin-bottom: 30px;
    padding: 10px 20px;
    }
    .ProductListOne ul{
        padding: 0;
    }
    .ProductListOne li{
        display: inline-block;
        margin-right: 10px;
        margin-top: 10px;
        padding: 20px;
        background: rgba(255,255,255,0.7);
        list-style:none;
    }
    .price{
        font-weight: bold;
        color: #E8800C;
    }
</style>
