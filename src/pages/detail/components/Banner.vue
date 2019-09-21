<template>
  <div>
    <div class="banner" @click="handleGallaryOpen">
      <img class="banner-img" :src="img"/>
      <div class="banner-info">
        <div class="info-title">{{sight}}</div>
        <div class="info-num">39
          <span class="iconfont">&#xe632;</span>
        </div>
      </div>
    </div>
    <common-gallary
    :gallaryList="imgs"
    v-show="showGallary"
    @close="handleGallaryClose"
    ></common-gallary>
  </div>
</template>

<script>
import CommonGallary from '@/common/gallary'
export default {
  name: 'DetailBanner',
  props: {
    sight: String,
    img: String,
    imgs: Array
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleGallaryOpen () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  },
  components: {
    CommonGallary
  }
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
