<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe624;</div>
    </div>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span>
      输入城市景点游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{city}}
        <span class="iconfont arron-icon">&#xe60e;</span>
      </div>
    </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'homeHeader',
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style scoped lang="stylus">
@import "~styles/varibles.styl"
.header
  display: flex
  line-height: $headerHeight
  background: $bgColor
  color: #fff
  .header-left
    width: .64 rem
    float: left
    .back-icon
      text-align: center
      font-size: .4rem
  .header-input
    padding-left: .2rem
    flex: 1
    background: #fff
    border-radius: 0.1rem
    margin-top: .12rem
    margin-left: .2rem
    line-height: .64rem
    height: .64rem
    color: #ccc
  .header-right
    min-width: 1.04 rem
    padding: 0 .1rem
    float: right
    text-align: center
    color: #fff
    .arron-icon
      font-size: .24rem
      margin-left: -.04rem
</style>
