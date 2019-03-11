<template>
  <div class="hello">
   <!-- <product-list-one v-bind:products="products"></product-list-one>
   <product-list-two v-bind:products="products"></product-list-two> -->
   <product-list-one></product-list-one>
   <product-list-two></product-list-two>
  </div>
</template>
<script>
import ProductListOne from './ProductListOne.vue'
import ProductListTwo from './ProductListTwo.vue'
export default {
  name: 'HelloWorld',
  components:{
    'product-list-one':ProductListOne,
    'product-list-two':ProductListTwo
  },
  data () {
    return {
     
    }
  },
  //  computed: {
  //   count () {
  //     return this.$store.state.count
  //   }
  // },
  // computed: mapState({
  //   // 箭头函数可使代码更简练
  //   count: state => state.count,

  //   // 传字符串参数 'count' 等同于 `state => state.count`
  //   countAlias: 'count',

  //   // 为了能够使用 `this` 获取局部状态，必须使用常规函数
  //   countPlusLocalState (state) {
  //     return state.count + this.localCount
  //   }
  // })
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
add 