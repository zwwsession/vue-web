<template>
  <div class="icons">
    <swiper>
      <swiper-slide v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img" >
            <img class="icon-img-content" :src="item.imgUrl"/>
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'homeIcons',
  props: {
    list: Array
  },
  data () {
    return {
    }
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style scoped lang='stylus'>
  @import "~styles/varibles.styl"
  @import "~styles/mixins.styl"
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 50%
  .icons
    margin-top: .1rem
    .icon
      position: relative
      overflow: hidden
      float: left
      width: 25%
      height: 0
      padding-bottom: 25%
      background: #fff
      .icon-img
        position: absolute
        top: 0
        left: 0
        right: 0
        box-sizing: border-box
        bottom: .44rem
        padding: .1rem
        .icon-img-content
          height: 100%
          margin: 0 auto
          display: block
      .icon-desc
        position: absolute
        bottom: 0
        left: 0
        right: 0
        line-height: .44rem
        color: $darkTextColor
        text-align: center
        ellipsis()
</style>
