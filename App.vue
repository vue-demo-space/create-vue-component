<template>
  <div>
    <count-to :end-val="10000" ref="countTo">
      <span slot="left">总金额：</span>
      <span slot="right">元</span>
    </count-to>
    <button @click="getNumber">获取当前值</button>
  </div>
</template>

<script>
import CountTo from './count-to'

export default {
  components: {
    CountTo
  },
  methods: {
    getNumber () {
      console.log(this.$refs.countTo.getCount())
    }
  }
}
</script>