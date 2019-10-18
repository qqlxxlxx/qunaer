<template>
  <div class="recommend-wrap">
    <h3 class="recommend-title border-bottom">去哪儿推荐</h3>
    <div class="recommend-item border-bottom"
         v-for="(item, index) of recommend" :key="index"
    >
      <div class="item-main">
        <h6 class="item-title">{{item.title}}</h6>
        <div class="item-time">
          <img class="time-icon" src="https://img1.qunarzz.com/piao/fusion/1804/25/792e9929973a9902.png" alt="">
          {{item.time}}
        </div>
      </div>
      <div class="item-side">
        <div class="item-price">
          ¥<em class="price-num">{{item.price}}</em>
        </div>
        <div class="item-btn">{{item.type}}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailRecommend',
  props: {
    recommend: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixin.styl'
  .recommend-wrap
    padding-left: .2rem
    .recommend-title
      padding: 0 .2rem
      height: .88rem
      background: url("../../../assets/img/rec.png") no-repeat left center/.36rem
      line-height: .88rem
      text-indent: .36rem
      font-size: .32rem
    .recommend-item
      display: flex
      padding: .2rem .2rem .24rem 0
      .item-main
        flex: 1
        color: #616161
        .item-title
          margin-right: .1rem
          line-height: .52rem
          font-size: .3rem
          ellipsis2()
        .item-time
          height: .32rem
          font-size: .24rem
          line-height: .32rem
          .time-icon
            width: .2rem
            max-height: .32rem
            margin-right: .04rem
            vertical-align: 0
      .item-side
        width: 1.8rem
        padding-left: .2rem
        box-sizing: border-box
        color: #ff9800
        .item-price
          margin-top: .3rem
          height: .4rem
          text-align: center
          .price-num
            margin-left: .04rem
            font-size: .4rem
        .item-btn
          height: .6rem
          background: linear-gradient(130deg,#ffab1e 37%,#ff8c12 100%)
          border-radius: .08rem
          line-height: .6rem
          font-size: .28rem
          color: #fff
          text-align: center
</style>
