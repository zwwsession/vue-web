<template>
  <div>
    <div class='title'>周末去哪儿</div>
    <ul>
      <li class='item border-bottom' v-for='item of list' :key='item.id'>
        <div class="item-image-wrapper">
          <img class='item-image' :src='item.imgUrl'/>
        </div>
        <div class='item-info'>
          <p class='item-title'>{{item.title}}</p>
          <p class='item-desc'>{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'weekend',
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
    text-indent: .2rem
  .item-image-wrapper
    overflow: hidden
    height: 0
    padding-bottom: 37.09%
    .item-image
      width: 100%
  .item-info
    padding: .1rem
    .item-titie
      line-height: .54rem
      font-size: .32rem
      ellipsis()
    .item-desc
      line-height: .4rem
      color: #ccc
      ellipsis()
</style>
