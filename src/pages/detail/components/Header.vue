<template>
  <div>
    <router-link tag="div" to="/" class="header-abs">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
    <div class="header-fixed" v-show="showAbs" :style="opacityStyle">景点详情
      <router-link to="/">
        <div class="iconfont Cback">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: false,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        this.showAbs = true
        let opacity = (top - 60) / 100
        this.opacityStyle = {opacity}
        opacity = opacity > 1 ? 1 : opacity
      } else {
        this.showAbs = false
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
.header-abs
  position: absolute
  top: .2rem
  left: .2rem
  width: .8rem
  height: .8rem
  text-align: center
  line-height: .8rem
  border-radius: .4rem
  background: rgba(0, 0, 0, 0.8)
  .header-back
    color: #ffffff
    font-size: .4rem
.header-fixed
  position: fixed
  top: 0
  left: 0
  right: 0
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
