<template>
  <div class="wrapper" ref="wrapper">
    <div class="content">
      <slot>
      </slot>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import ObserveDOM from '@better-scroll/observe-dom'

BScroll.use(ObserveDOM)
export default {
  name: "Scroll",
  props: {
    //父传子，props  子传父
    probeType: {
      type: Number,
      default: 0
    },
    pullUpLoad: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      scroll: null
    }
  },
  mounted() {
    this.scroll = new BScroll(this.$refs.wrapper, {
      observeDOM: true,
      click: true,
      probeType: this.probeType
      , pullUpLoad: this.pullUpLoad
    })
    //2监听滚动位置
    this.scroll.on("scroll", (position) => {
      this.$emit("scroll", position)
    })
    this.scroll.on("pullingUp", () => {
      this.$emit(("pullingup"))
    })
  },
  methods: {
    scrollTo(x, y, time = 300) {
      this.scroll.scrollTo(x, y, time)
    },
    finishPullUp(){
      this.scroll.finishPullUp()
    }
  }
}
</script>

<style scoped>

</style>