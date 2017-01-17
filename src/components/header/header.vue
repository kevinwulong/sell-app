<template>
<div class="header">
  <div class="contnet-warpper">
    <div class="avatar">
      <img width="64" height="64" :src="seller.avatar">
    </div>
  </div>
  <div class="bulletin-warpper">
  	
  </div>
</div>
</template>

<script type="text/ecmascript-6">
  export default{
    props: {
      seller: {
        type: Object
      }
    }
  }
</script>

<style lang="stylus" rel='stylesheet/stylus'>
	
</style>