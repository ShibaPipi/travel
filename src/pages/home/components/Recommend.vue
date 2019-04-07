<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.imgUrl" alt="">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">￥{{item.desc}}起</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        id: '0001',
        title: '天津方特欢乐世界',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1711/e1/e14af792aca4f7b3a3.water.jpg_200x200_461cbb00.jpg',
        desc: '260'
      }, {
        id: '0002',
        title: '天津欢乐谷',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1703/76/76f0136dc779efdda3.img.jpg_200x200_ef96dcaf.jpg',
        desc: '130'
      }, {
        id: '0003',
        title: '天津海昌极地海洋公园',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1809/6b/6b900de5e5ac7239a3.img.jpg_200x200_98bbdd13.jpg',
        desc: '165'
      }, {
        id: '0004',
        title: '天津龙达温泉生态城',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1411/61/84f6158c7843d6a451d4c8d9b6fe1fa2.water.jpg_200x200_ef9c8e4c.jpg',
        desc: '88'
      }, {
        id: '0005',
        title: '天津热带植物观光园',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/201401/20/7f46618dcfabc20589795bf6f54ba8ea.jpg_200x200_30d8e134.jpg',
        desc: '89'
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
  .item
    display flex
    height 1.9rem
    overflow hidden
    .item-img
      width 1.7rem
      height 1.7rem
      padding .1rem
    .item-info
      flex 1
      padding .1rem
      min-width 0
      .item-title
        line-height .54rem
        font-size .32rem
        ellipsis()
      .item-desc
        line-height .4rem
        color #ccc
        ellipsis()
      .item-button
        line-height .44rem
        margin-top .16rem
        background #ff9300
        padding 0 .2rem
        border-radius .06rem
        color #fff
</style>
