<!-- 兑换方法 -->
<template>
  <div class="popup dhff"/>
</template>
<script>
  // import text_limit from '~/assets/img/text/text_popup_limit.png'
  // 领取成功
  import text from '~/assets/img/text/text_gxnjdfl.png'
  import icon from '~/assets/img/icon/icon_gxxz.png'
  import btn from '~/assets/img/btn/btn_yydhh.png'

  const EVENT_CLOSE = 'close'
  export default {
    props: {
      type: {
        type: String, // success/limit
        default: ''
      }
    },
    data () {
      return {
        text,
        icon,
        btn,
      }
    },
    computed: {
    },
    methods: {
      close (e) {
        this.$emit(EVENT_CLOSE, e)
      },
      // 跳转至预约兑换页面
      exchange () {
        // this.$router.push(`/${name}`)
      }
    }
  }
</script>
<style scoped lang="stylus" rel="stylesheet/stylus">
  .popup.dhff
    width: 412px
    height: 654px
    overflow: hidden
    background: url('~assets/img/bg/popup_dhff.png') no-repeat
    background-size: 412px 654px
    display: flex
    justify-content: center
    flex-direction: column
    text-align: center
    align-items: center
    .icon
      margin-top: 130px
      width: 186px
      height: 164px
    .text
      position: absolute
      top: 200px
      width: 303px
      height: 78px

    .buttons
      position: absolute
      bottom: 80px
      width: 292px
      display: flex
      justify-content: center
      img
        width: 266px
        height: 64px
</style>
