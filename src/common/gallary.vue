<template>
  <div class="gallary-bacon" @click="handleGallaryClick">
    <div class="gallary-item">
      <swiper :options="swiperOption">
        <swiper-slide v-for="(item, index) of gallaryList" :key="index">
          <img class="gallary-img" :src="item"/>
        </swiper-slide>
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    gallaryList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
.gallary-bacon >>> .swiper-container
  overflow: inherit
.gallary-bacon
  z-index: 99
  display: flex
  flex-direction: column
  justify-content: center
  position: fixed
  left: 0
  right: 0
  top: 0
  bottom: 0
  background: black
  .gallary-item
    background: white
    height: 0
    width: 100%
    padding-bottom: 100%
    .gallary-img
      width: 100%
    .swiper-pagination
      color: #fff
      bottom: -1rem
</style>
