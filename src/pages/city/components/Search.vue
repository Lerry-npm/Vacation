<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音"/>
    </div>
    <div class="search-content" ref="search" v-show="keyword">
      <ul>
        <li
        class="item border-bottom"
        v-for="item of list"
        :key="item.id"
        @click="handleChangeCity(item.name)"
        >{{item.name}}</li>
        <li class="item border-bottom" v-show="hasList">没有匹配数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasList () {
      return !this.list.length
    }
  },
  methods: {
    handleChangeCity (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search)
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        const result = []
        if (this.keyword) {
          for (let i in this.cities) {
            this.cities[i].forEach((value) => {
              if (value.spell.indexOf(this.keyword) > -1 ||
              value.name.indexOf(this.keyword) > -1) {
                result.push(value)
              }
            })
          }
        }
        this.list = result
      }, 100)
    }
  }
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
.search-content
  z-index: 1
  position:absolute
  overflow: hidden
  top: 1.58rem
  left: 0
  right: 0
  bottom: 0
  background: #eee
  .item
    line-height: .52rem
    background: #fff
    padding-left: .2rem
</style>
