<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
    .header
      position: relative
      overflow: hidden
      height: .88rem
      line-height: .88rem
      background: $bgColor
      text-align: center
      color: #fff
      font-size: .32rem
      .header-back
        position: absolute
        top: 0
        left: 0
        width: .8rem
        text-align: center
        font-size: .36rem
        font-weight: bold
        color: #fff
</style>
