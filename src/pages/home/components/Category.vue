<template>
  <div class="icons border-bottom">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl" alt="">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeCategory',
  props: {
    list: Array
  },
  data() {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: false
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if(!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixin.styl'
  .icons >>> .swiper-container
    height: 3.7rem
  .icons >>> .swiper-pagination-bullet
    width: .12rem
    height: .12rem
    opacity: 0.3
  .icons >>> .swiper-pagination-bullet-active
    background: rgb(0, 175, 190)
    opacity: 1
  .icons
    overflow: hidden
    margin-top: .1rem
    height: 3.7rem
    .icon
      float: left
      width: 25%
      height: 1.5rem
      padding-top: .1rem
      text-align: center
      .icon-img
        display: inline-block
        width: 1rem
        height: 1rem
        .icon-img-content
          height: 100%
      .icon-desc
        overflow: hidden
        margin-top: .1rem
        font-size: .28rem
        color: $darkTextColor
        white-space: nowrap
        ellipsis()
</style>
