<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide  v-for="(page, index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img-content">
            <img class="icon-img" :src="item.imgUrl">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
       </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
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
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/stylus/varible.styl';
@import '~styles/stylus/mixins.styl';
  .icons >>> .swiper-slide-active
    height :0
    padding-bottom :50%
  .icon
    position :relative
    height :0
    float :left
    padding-bottom :25%
    width :25%
    overflow :hidden
    .icon-img-content
      position: absolute
      top :0
      left :0
      right :0
      bottom :.44rem
      box-sizing :border-box
      padding :.18rem
      .icon-img
        display :block
        height :100%
        margin :0 auto
    .icon-desc
      position :absolute
      right :0
      left :0
      bottom :0
      height :.44rem
      line-height :.44rem
      text-align :center
      color :$darkTextColor
      ellipsis()
</style>
