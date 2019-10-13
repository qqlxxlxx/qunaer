<template>
  <div>
    <div class="title">
      <img class="title-img" src="https://imgs.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
      猜你喜欢
    </div>
    <ul class="lists">
      <router-link :to="'/detail/'+item.id" tag="li"
                   class="item border-bottom"
                   v-for="item of list" :key="item.id"
      >
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" alt="">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <div class="item-price">
            <span>￥<em class="price-num">54</em></span>起
          </div>
          <div class="item-desc">{{item.desc}}</div>
        </div>
      </router-link>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
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
    .title-img
      width: .3rem
      height: .3rem
      vertical-align: top
  .lists
    margin-left: .24rem
    .item
      overflow: hidden
      display: flex
      height: 2rem
      padding: .2rem 0
      .item-img-wrapper
        width: 2rem
        height: 2rem
        .item-img
          width: 100%
      .item-info
        flex: 1
        min-width: 0
        padding-left: .22rem
        .item-title
          margin-top: .26rem
          height: .44rem
          line-height: .44rem
          font-size: .32rem
          ellipsis()
        .item-price
          margin-top: .22rem
          font-size: .24rem
          line-height: .4rem
          span
            color: #ff8300
            .price-num
              font-size: .4rem
        .item-desc
          display: inline-block
          margin-top: .24rem
          background: #fff9f9
          color: #f55
          font-size: .24rem;
          line-height: .34rem
          ellipsis()
</style>
