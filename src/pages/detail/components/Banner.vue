<template>
  <div class="banner">
    <img class="banner-img" src="https://tr-osdcp.qunarzz.com/tr-osd-tr-manager/img/7d9b233c71cad13ded0013f9c9cec635.jpg"/>
    <div class="banner-info">
      <div class="info-title">大连海洋馆AAA</div>
      <div class="info-num">39
        <span class="iconfont">&#xe632;</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailBanner'
}
</script>

<style lang="stylus" scoped>
.banner
  position: relative
  overflow: hidden
  height: 0
  padding-bottom: 55%
  .banner-img
    width: 100%
  .banner-info
    display: flex
    position: absolute
    left: 0
    right: 0
    bottom: 0
    line-height: .6rem
    .info-title
      flex: 1
      color: #fff
      font-size: .32rem
      padding: 0 .2rem
    .info-num
      color: #fff
      padding: 0 .4rem
      margin-top: .14rem
      height: .32rem
      line-height: .32rem
      border-radius: .06rem
      background: rgba(0, 0, 0, 0.8)
</style>
