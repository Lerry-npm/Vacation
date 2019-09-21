<template>
  <div>
    <div v-for="(item, index) of list" :key="index">
      <div class="list-title border-bottom">
        <span class="list-icon"></span>
        {{item.title}}
      </div>
      <div v-if="item.children" class="list-children">
        <detail-list :list="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
.list-title
  height: .8rem
  line-height: .8rem
  font-size: .32rem
  padding: 0 .2rem
.list-icon
  position: relative
  left: .06rem
  top: .06rem
  display: inline-block
  width: .36rem
  height: .36rem
  background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
  margin-right: .1rem
  background-size: .4rem 3rem
.list-children
  padding: 0 .2rem
</style>
