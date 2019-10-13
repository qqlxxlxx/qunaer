<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul class="lists">
    	<li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixin.styl'
  .title
    padding: .24rem 0 .26rem
    height: .44rem
    background: #f2f2f2
    line-height: .44rem
    font-size: .32rem
    text-indent: .2rem
  .item
    margin-bottom: .1rem
    .item-img-wrapper
      overflow: hidden
      height: 0
      padding-bottom: 36.65%
      .item-img
        width: 100%
    .item-info
      padding: .14rem .2rem .2rem .2rem
      .item-title
        line-height: .48rem
        font-size: .28rem
        ellipsis()
      .item-desc
        line-height: .42rem
        font-size: .24rem
        color: #616161
        ellipsis()
</style>
