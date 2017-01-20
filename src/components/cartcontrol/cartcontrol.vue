<template>
  <div class="cartcontrol"> 
    <div class="cart-decrease" v-show="food.count>0" @click="decreaseCart">卖</div>
    <div class="cart-count" v-show="food.count>0">{{food.count}}</div>
    <div class="cart-add" @click="addCart">买</div>
  </div>
</template>

<script type="text/ecmascript-6">
  import Vue from 'vue'
  export default {

    props: {
      food: {
        type: Object
      }
    },
    methods: {
      addCart(event) {
        if (!event._constructed){
          return
        }
        if (!this.food.count){
          Vue.set(this.food, 'count', 1)
          this.food.count= 1
        }
        else {
          this.food.count++
        }
      },
      decreaseCart(event) {
        if (!event._constructed){
          return
        }
        if (this.food.count){
          this.food.count--
        }
      }
    }
  }
</script>

<style lang="stylus" rel='stylesheet/stylus'>
  .cartcontrol
    font-size: 0
    .cart-decrease, .cart-add
      display: inline-block
      line-height: 13px
      font-size: 13px
      padding: 6px
    .cart-count
      display: inline-block
      vertical-align: top
      width:12px
      padding-top:6px
      line-height:14px
      text-align: center
      font-size:10px
      color:rgb(147,153,159)
    .cart-add
      display: inline-block

</style>