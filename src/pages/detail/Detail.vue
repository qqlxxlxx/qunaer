<template>
  <div>
    <detail-banner :sightName="sightName" :bannerImg="bannerImg" :bannerImgs="gallaryImgs" />
    <detail-header />
    <div class="content">
      <detail-recommend :recommend="recommend"></detail-recommend>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailRecommend from './components/Recommend'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailRecommend
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      recommend: []
    }
  },
  methods: {
    getDetailInfo () {
      let id = this.$route.params.id
      axios.get('/api/detail/'+id+'.json').then(this.handleGetDataSucc)
    },
    handleGetDataSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.recommend = data.recommendInfo
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem
</style>
