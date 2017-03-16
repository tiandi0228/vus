<template>
  <div :class="[myResult ? show : hide]">
    <div @click="ok">确认</div>
    <div>{{myResult ? '开' : '关'}}</div>
  </div>
</template>

<script>
export default {
  props: ["result"],
  data: function () {
    return {
      myResult: this.result,
      show: 'show',
      hide: 'hide'
    }
  },
  mounted() {
    console.log(this.myResult)
  },
  watch: {
    result(val) {
      this.myResult = val
    },
    myResult(val){
      this.$emit("on-result-change",val)
    }
  },
  methods: {
    ok() {
      this.myResult = !this.myResult
    }
  }
}
</script>

<style lang="less">
  h1, h2 {
    font-weight: normal;
  }

  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline-block;
    margin: 0 10px;
  }

  a {
    color: #42b983;
  }
  .show{
    display: block;
  }
  .hide{
    display: none;
  }
</style>
