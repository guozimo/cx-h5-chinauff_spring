<!-- 6.2.3、继续邀请好友助力 -->
<template>
  <c-page>
    <div
      slot="content"
      class="page623">
      <top-buttons type="second"/>
      <span class="title"/>
      <div class="content">
        <div class="info">
          <div class="members members--overlap">
            <ul>
              <li
                v-for="(item, index) in headimgs"
                :key="index"
                class="member">
                <img
                  :src="item"
                  class="c-avatar c-avatar-image">
              </li>
            </ul>
          </div>
          <span class="moredot">••••••</span>
          <div class="total">
            <img
              src="~assets/img/page621/deng.png"
              class="text-deng">
            <span class="count">{{ total }}</span>
            <img
              src="~assets/img/page621/weihaoyou.png"
              class="text-weihaoyou">
          </div>
          <img
            src="~assets/img/page623/text_yqcyjf.png"
            class="text-yqcyjf">
        </div>
        <div class="actions">
          <img
            src="~assets/img/btn/btn_jxyqhyzl.png"
            class="btn_jxyqhyzl">
            <!--<img-->
            <!--src="~assets/img/text/text_djccqwjf.png"-->
            <!--class="text-djccqwjf">-->
        </div>

      </div>
      <div class="footer"/>
    </div>
  </c-page>
</template>
<script>
  import CPage from '../components/c-page.vue'
  import {isBrowser} from '~/environment_es'
  import TopButtons from '../components/top-buttons'
  import PageContent from '../components/page-content'
  import tip1 from '~/assets/img/text/text_gxnjd.png'
  import tip2 from '~/assets/img/text/text_gxncz.png'

  export default {
    name: 'Index',
    head () {
      return {
        title: '老娘舅新春集福瓜分18吨福米'
      }
    },
    components: {
      CPage,
      TopButtons,
      PageContent
    },
    props: {
      coupon: {
        type: String,
        default: 'mianfei'
      },
      word: {
        type: String,
        default: 'kou'
      }
    },
    data () {
      return {
        total: '12,345',
        count: '2',
        tip1,
        tip2,
        limit: 2,
        headimgs: [
          'https://i.loli.net/2017/08/21/599a521472424.jpg',
          'https://i.loli.net/2017/08/21/599a521472424.jpg',
          'https://i.loli.net/2017/08/21/599a521472424.jpg',
          'https://i.loli.net/2017/08/21/599a521472424.jpg',
          'https://i.loli.net/2017/08/21/599a521472424.jpg',
        ]
      }
    },
    computed: {
      _couponClass () {
        return [
          'coupon',
          'coupon-' + this.coupon
        ]
      },
      _wordClass () {
        return [
          'word',
          'word-' + this.word
        ]
      }
    },
    methods: {
      showAlert () {
        this.dialog = this.$createDialog({
          type: 'intro',
          showClose: true
        })
        this.dialog.show()
      }
    },
  }
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">


  .page623
    color: $color-dark
    display: flex
    align-items: center
    flex-direction: column
    min-height: 100vh
    position: absolute
    left: 0
    width: 100%
    height: 100%
    justify-content: space-between
    overflow: hidden
    background: url('~assets/img/page621/topbg.png') no-repeat left top
    background-size: 566px 301px

    .title
      top: 50px
      position: relative
      background: url('~assets/img/page621/biaoti.png') no-repeat left top
      width: 340px
      height: 135px
      background-size: 340px 135px

    .content
      z-index: 0
      position: relative
      top: 60px
      display: flex
      flex-direction: column
      justify-content: space-between
      align-items: center
      background: url('~assets/img/page621/tcbg.png') no-repeat left top
      background-size: 394px 584px
      width: 394px
      height: 600px
      .info
        position: relative
        top: 160px
        display: flex
        flex-direction: column
        justify-content space-between
        align-items: center
        .total
          color: $color-white
          font-size: 21px
          display: flex
          flex-direction: row
          justify-content: center
          margin-bottom: 50px
          .count
            font-weight: 500
            margin: 0 4px 0 4px
          .text-deng
            width: 18px
            height: 21px
          .text-weihaoyou
            width: 128px
            height: 21px
      .actions
        display: flex
        flex-direction: column
        justify-content: center
        position: relative
        bottom: 50px
        .btn_jxyqhyzl
          width: 218px
          margin-bottom: 20px
        .text-djccqwjf
          width: 230px
          height: 27px
      .text-yqcyjf
        width: 286px
        height: 53px
      .text-zhulizhuli
        width: 185px
        height: 53px
      .moredot
        color: $color-white
        letter-spacing: 3px
        font-size: 18px
        padding: 10px
      .members
        ul
          float: left
        &--overlap
          .member
            margin-left: -15px
            float: right
            font-size: 10px
      .c-avatar
        display: inline-block
        text-align: center
        background: #ccc
        color: #fff
        white-space: nowrap
        position: relative
        overflow: hidden
        vertical-align: middle
        width: 48px
        height: 48px
        /*line-height: 32px*/
        border-radius: 100%
        border: 3px solid #fff

        > img
          width: 100%
          height: 100%

        &-image
          background: 0 0

    .footer
      z-index: 2
      background: url('~assets/img/page621/bottombg.png') no-repeat left bottom
      background-size: 640px 292px
      width: 640px
      height: 292px

</style>
