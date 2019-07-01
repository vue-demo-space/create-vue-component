<template>
  <div>
    <slot name="left"/>
    <span ref="number" :id="eleId"></span>
    <slot name="right"/>
  </div>
</template>

<script>
import CountUp from 'countup'

export default {
  name: 'count_to',
  data () {
    return {
      eleId: `count_up_${this._uid}`,
      counter: {}
    }
  },
  props: {
    /**
     * @description 起始值
     */
    startVal: {
      type: Number,
      default: 0,
    },
    /**
     * @description 最终值
     */
    endVal: {
      type: Number,
      required: true,
    },
    /**
     * @description 小数点后保留几位小数
     */
    decimals: {
      type: Number,
      default: 0,
    },
    /**
     * @description 渐变时长
     */
    duration: {
      type: Number,
      default: 2,
    }
  },
  mounted () {
    this.counter = new CountUp(this.eleId, this.startVal, this.endVal, this.decimals, this.duration)
    this.counter.start()
  },
  methods: {
    getCount () {
      return this.$refs.number.innerText
    }
  }
}
</script>