<template>
  <div>
    <div class="title">热销推荐</div>
    <div class="item border-bottom" v-for="item of list" :key="item.id">
      <img class="item-img" :src="item.imgUrl"/>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
        <button class="item-button">查看详情</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
.title
  line-height: .44rem
  background: #eee
  padding: .1rem
  text-indent: .2rem
.item
  display: flex
  overflow: hidden
  height: 1.9rem
  .item-img
    height: 1.7rem
    width: 1.7rem
    margin: .1rem
  .item-info
    flex: 1
    padding: .1rem
    .item-title
      line-height: .54rem
      font-size: .32rem
    .item-desc
      color: #ccc
      line-height: .44rem
    .item-button
      background: #ff9300
      margin-top: .16rem
      padding: 0 .2rem
      border-radius: .06rem
      line-height: .44rem
</style>
