<template>
  <div>
    <div class="title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [{
        id: '0001',
        title: '天津踏青好去处',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1603/7d/ec3464884611b6.jpg_r_640x214_97e4e35f.jpg',
        desc: '这个春天，属于天津的美丽'
      }, {
        id: '0002',
        title: '天津必打卡',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1603/5b/b0488000889ed2.jpg_r_640x214_e53fa939.jpg',
        desc: '到此领略北方港口城市的魅力'
      }, {
        id: '0003',
        title: '周末亲子玩乐',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1605/9f/8026e2ec9f2c3c.jpg_r_640x214_22c0e0e3.jpg',
        desc: '周末就带宝贝玩乐吧！快来让宝贝与海洋动物亲密接触，观看海豚海狮精彩滑稽的表演'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title
    margin-top .2rem
    line-height .8rem
    text-indent .2rem
    background #eee
    .item-img-wrapper
      overflow hidden
      height 0
      padding-bottom 33.9%
  .item-img
    width 100%
  .item-info
    padding .2rem
    .item-title
      line-height .54rem
      font-size .32rem
      ellipsis()
    .item-desc
      line-height .4rem
      margin-bottom .1rem
      font-size .1rem
      color #616161
      ellipsis()
</style>
