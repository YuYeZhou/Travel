<template>
  <ul class="list">
    <li class="item"
    v-for="letter of letters"
    :key="letter"
    :ref="letter"
    @click="handleLetterClick"
    @touchstart="handleTouchStart"
    @touchmove="handleTouchMove"
    @touchend="handleTouchEnd"
    >{{letter}}</li>
  </ul>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  data () {
    return {
      touchStatus: false,
      startY: '',
      time: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleLetterClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        const startY = this.startY
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - 79
          const index = Math.floor((touchY - startY) / 20)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/stylus/varible.styl'
  .list
    display :flex;
    flex-direction :column
    justify-content :center
    position :absolute
    top :1.58rem
    bottom 0
    right 0
    width :.4rem
    .item
      color :$bgColor
      line-height :.4rem
      text-align :center
</style>
