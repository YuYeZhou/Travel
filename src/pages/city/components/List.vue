<template>
  <div class="list"  ref="wrapper">
    <div>
      <div class="aera">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper" @click="backToHome">
            <div class="button">{{this.currentCity}}</div>
          </div>
        </div>
      </div>
      <div class="aera">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper" v-for="city of hot" :key="city.id" @click="handleCityClick(city.name)">
            <div class="button">{{city.name}}</div>
          </div>
        </div>
      </div>
      <div class="aera"  v-for="(item, key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
          <div class="item-list">
            <div class="item border-bottom" v-for="city of item" :key="city.id" @click="handleCityClick(city.name)">{{city.name}}</div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hot: Array,
    letter: String
  },
  methods: {
    backToHome () {
      this.$router.push('/')
    },
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  computed: {
    ...mapState({
      currentCity: 'city'
    }),
    ...mapMutations
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/stylus/mixins.styl'
  .border-topbottom
    &:before
      border-color :#ccc
    &:after
      border-color :#ccc
  .border-bottom
    &:before
      border-color :#ccc
  .list
    overflow :hidden
    position :absolute
    top :1.58rem
    left 0
    right 0
    bottom 0
    .title
      background :#eee
      padding-left :.2rem
      line-height :.54rem
      color :#666
      font-size :.26rem
    .button-list
      padding :.1rem .6rem .1rem .1rem
      overflow :hidden
      .button-wrapper
        float :left
        width :33.33%
        .button
          border-radius :.06rem
          padding .1rem
          margin :.1rem
          text-align :center
          border :.02rem solid #ccc
    .item-list
      line-height :.76rem
      color :#666
      .item
        padding-left :.2rem
</style>
