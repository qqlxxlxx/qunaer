<template>
  <div class="container" @click="handGallaryClick">
    <swiper class="wrapper" :options="swiperOption">
      <swiper-slide v-for="(item, index) of imgs" :key="index">
        <div class="gallary-img" :style="{background:'url('+item+') no-repeat left center/100% auto'}"></div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'CommonGallary',
  props: {
    imgs: {
      type: Array,
      default() {
        return []
      }
    }
  },
  data() {
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
    handGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
  .container
    display: flex
    flex-direction: column
    justify-content: center
    position: fixed
    left: 0
    right: 0
    top: 0
    bottom: 0
    z-index: 99
    background: #000
    .wrapper
      width: 100%
      height: 100%
      .gallary-img
        width: 100%
        height: 100vh
      .swiper-pagination
        bottom: .7rem
        color: #fff
</style>
