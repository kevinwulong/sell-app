<template>
  <div>
      <z-header :seller="seller"></z-header>
      <div class="tab border-1px"></div>
      <z-tab></z-tab>
  </div>
</template>

<script>
  import header from './components/header/header'
  import tab from './components/header/tab'

  const ErrOk= 0

  export default{
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
      'z-tab': tab
    }
  }
</script>

<style lang="stylus" rel='stylesheet/stylus'>
    
</style>
