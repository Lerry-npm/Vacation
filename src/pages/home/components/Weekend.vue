<template>
  <div>
    <div class="title">周末去哪儿</div>
    <div class="weekend border-bottom" v-for="item of weekendList" :key="item.id">
      <img class="weekend-img" :src="item.imgUrl"/>
      <p class="weekend-title">{{item.title}}</p>
      <p class="weekend-desc">{{item.desc}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      weekendList: [{
        id: '0001',
        imgUrl: 'https://imgs.qunarzz.com/p/tts5/1808/71/51effca6fc1f5a02.jpg_r_390x260x90_85417729.jpg',
        title: '温泉水上乐园',
        desc: '体验家庭版豪华水上活动'
      }, {
        id: '0002',
        imgUrl: 'https://imgs.qunarzz.com/p/tts5/1808/71/51effca6fc1f5a02.jpg_r_390x260x90_85417729.jpg',
        title: '温泉水上乐园',
        desc: '体验家庭版豪华水上活动'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
.title
  line-height: .44rem
  background: #eee
  padding: .1rem
  text-indent: .2rem
.weekend
  height: 3.2rem
  .weekend-img
    height: 2.1rem
    width: 100%
  .weekend-title
    font-size: .32rem
    margin-top: .2rem
    padding-left: .2rem
  .weekend-desc
    color: #ccc
    padding: .2rem
</style>
