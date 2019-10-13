<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="bannerImg" alt="">
      <div class="banner-info">
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe692;</span>
          {{this.bannerImgs.length}}
        </div>
        <div class="banner-title">{{this.sightName}}</div>
      </div>
    </div>
    <fade-animation>
      <common-gallary :imgs="bannerImgs" v-show="showGallary" @close="handleGallaryClose" />
    </fade-animation>
  </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallary,
    FadeAnimation
  },
  props: {
    sightName: String,
    bannerImg: String,
    bannerImgs: Array
  },
  data () {
    return {
      showGallary: false
    }
  },
  methods: {
    handleBannerClick () {
      this.showGallary = true
    },
    handleGallaryClose () {
      this.showGallary = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    &::after
      content: ""
      display: block
      position: absolute
      left: 0
      bottom: 0
      width: 100%
      min-height: .7rem
      background: linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,.8))
    .banner-img
      width: 100%
    .banner-info
      position: absolute
      left: .2rem
      left: .2rem
      bottom: 0rem
      z-index: 1
      color: #fff
      .banner-title
        font-size: .36rem
        margin-bottom: .36rem
      .banner-number
        margin-bottom: .12rem
        width: 1.2rem
        height: .4rem
        line-height: .4rem
        border-radius: .2rem
        background: rgba(0,0,0,.5)
        text-align: center
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
