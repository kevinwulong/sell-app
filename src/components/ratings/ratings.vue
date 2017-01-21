<template>
  <div>
    <z-header  :seller='seller'></z-header>
    <z-tab></z-tab>
    <div> ratings!!</div>
  </div>
 
</template>

<script>
  import header from '../header/header'
  import tab from '../header/tab'
  
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
      'z-tab': tab
}
}
</script>

<style lang="stylus" rel='stylesheet/stylus'>
	
</style>