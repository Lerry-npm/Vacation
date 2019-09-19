<template>
  <div class="item">
    <div class="item-list" v-for="(item,key) of cities" :key="key">{{key}}</div>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
.item
  display: flex
  flex-direction: column
  justify-content: center
  position: absolute
  width: .44rem
  top: 1.58rem
  right: 0
  bottom: 0
  color: #00bcd4
  .item-list
    height: .4rem
    text-align: center
</style>
