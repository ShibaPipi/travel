<template>
  <div>
    <detail-banner
      :sightName="sightName"
      :bannerImg="bannerImg"
      :galleryImgs="galleryImgs"
    ></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
import { mapState } from 'vuex'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      lastId: '',
      sightName: '',
      bannerImg: '',
      galleryImgs: [],
      list: []
    }
  },
  computed: {
    ...mapState(['id'])
  },
  methods: {
    getDetailInfo () {
      axios.get('api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getDataSucc)
    },
    getDataSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.galleryImgs = data.galleryImgs
        this.list = data.categoryList
      }
    }
  },
  mounted () {
    this.lastId = this.id
    this.getDetailInfo()
  },
  activated () {
    if (this.lastId !== this.id) {
      this.lastId = this.id
      this.getDetailInfo()
    }
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height 120rem
</style>
