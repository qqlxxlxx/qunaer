<template>
  <div>
    <div class="header-abs" v-show="showAbs" @click="backHome">
      <div class="iconfont header-abs-back">&#xe624;</div>
    </div>
    <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
      <div @click="backHome">
        <div class="iconfont header-fixed-back">&#xe624;</div>
      </div>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: 0
    }
  },
  methods: {
    handleScroll () {
      const top = window.pageYOffset || document.documentElement.scrollTop || document.body.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = {
          opacity
        }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    },
    backHome () {
      this.$router.back();
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  destroyed () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-abs
    position: absolute
    left: .1rem
    top: .1rem
    width: .72rem
    height: .72rem
    border-radius: .4rem
    background: rgba(0,0,0,.5)
    .header-abs-back
      line-height: .72rem
      text-align: center
      font-size: .34rem
      font-weight: bold
      color: #fff
  .header-fixed
    position: fixed
    top: 0
    left: 0
    right: 0
    z-index: 2
    height: $headerHeight
    line-height: $headerHeight
    background: $bgColor
    text-align: center
    color: #fff
    .header-fixed-back
      position: absolute
      top: 0
      left: 0
      width: .88rem
      font-size: .34rem
      font-weight: bold
</style>
