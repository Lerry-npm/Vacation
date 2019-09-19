<template>
  <div class="header">
    <div class="header-text">城市选择</div>
    <router-link to="/">
      <div class="iconfont Cback">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
.header
  position: relative
  overflow: hidden
  height: .86rem
  line-height: .86rem
  background: #00bcd4
  color: #fff
  text-align: center
  font-size: .32rem
  .Cback
    position: absolute
    top: 0
    left: .2rem
    font-size: .4rem
    text-align: center
    color: #fff
</style>
