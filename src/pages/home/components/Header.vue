<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.$store.state.city}}
        <span class="iconfont city">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
.header
  display: flex
  line-height: .86rem
  background: #00bcd4
  color: #fff
  .header-left
    float: left
    width: .64rem
    .back
      text-align: center
      font-size: .4rem
  .header-input
    flex: 1
    margin-top: .12rem
    margin-left: .2rem
    padding-left: .2rem
    height: .64rem
    line-height: .64rem
    border-radius: .1rem
    background: #fff
    color: #ccc
  .header-right
    float: right
    min-width: 1.28rem
    text-align: center
    color: #fff
    .city
      font-size: .24rem
      margin-left: -.04rem
</style>
