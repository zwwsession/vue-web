<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <img class='item-image' :src="item.imgUrl"/>
        <div class='item-info'>
          <p class='item-titlen'>{{item.title}}</p>
          <p class='item-desc'>{{item.desc}}</p>
          <button class='item-buttom'>查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'recommend',
  props: {
    list: Array
  },
  data () {
    return {
    }
  }
}
</script>

<style scoped lang='stylus'>
  @import '~styles/mixins.styl'
  .title
    line-height: .8rem
    background: #eee
    margin-top: .2rem
    text-indent: .2rem
  .item
    display: flex
    height: 1.9rem
    overflow: hidden
    .item-image
      width: 1.7rem
      height: 1.7rem
      padding .1rem
    .item-info
      margin-top: .2rem
      padding: .1rem
      flex: 1
      min-width: 0
      .item-titie
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-buttom
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
