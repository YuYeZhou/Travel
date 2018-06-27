<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/1c/4847ea66072c7b02.jpg_750x200_c32457fb.jpg'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1806/fc/e47aa3e1c67bbc02.jpg_750x200_0f3eecf8.jpg'
      }],
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        },
        loop: true
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background :#fff
  .wrapper
    width :100%
    overflow :hidden
    height :0
    padding-bottom :26.66%
    background :#eee
    .swiper-img
      width :100%
</style>
