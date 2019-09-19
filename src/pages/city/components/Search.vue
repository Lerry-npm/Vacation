<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="输入城市名或拼音"/>
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
.search
  height: .72rem
  line-height: .72rem
  background: #00bcd4
  color: #fff
  .search-input
    box-sizing: border-box
    width: 95%
    margin-left: .15rem
    height: .52rem
    line-height: .52rem
    padding: 0 .1rem
    text-align: center
    border-radius: .06rem
    color: #666
</style>
