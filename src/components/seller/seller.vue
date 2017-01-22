<template>
<div>
    <z-header :seller='seller'></z-header>
    <z-tab></z-tab>
    <div class="seller">维护中。。
    </div>
</div>
</template>

<script>
  import header from '../header/header'
  import tab from '../header/tab'
  import star from '../star/star'
  const ErrOk= 0

  export default {
    
    data () {
      return {
        seller: {}
      }
    },
    created () {
      this.$http.get('/api/seller').then((response) => {
        response = response.body
        if (response.errno === ErrOk) {
          this.seller = response.data
          console.log(this.seller)
        }
      })
    },
    components: {
      'z-header': header,
      'z-tab': tab,
      'z-star': star
}
}
</script>

<style lang="stylus" rel='stylesheet/stylus'>
  @import "../../common/stylus/mixin"
  .seller 
       position: absolute
       top:174px 
       bottom:0
       width:100%
       left:0
       overflow: hidden
       .overview
             padding: 18px
             .title
                   maring-bottom: 8px
                   line-height: 14px
                   color:rgb(7,17,27)
                   font-size: 14px
             .desc
                   padding-bottom:18px
                   line-height: 18px
                   border-1px(rgba(7,17,27,0.1))
                   font-size:0
                   .star
                         display:inline-block
                         margin-right: 8px
                         vertical-align: top
                   .text
                         margin-right: 12px
                         vertical-align: top
                         font-size:10px


</style>