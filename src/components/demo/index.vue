<template>
  <div class="hello">
    <h1>{{ text }}</h1>
  </div>
</template>

<script lang="ts">
import { defineComponent, onMounted, reactive, toRefs } from 'vue'
import { useStore } from 'vuex'
export default defineComponent({
  name: 'Home',
  props: {
    msg: String
  },
  setup (props, ctx) {
    // 获取 vuex 实例
    const store = useStore()
    // 声明数据
    const state: {
      text: String
    } = reactive({
      text: ''
    })
    // ready
    onMounted (() => {
      state.text = props.msg + '---' + store.state.app.count
      // setInterval(() => {
      //   state.text = props.msg + '---' + store.state.app.count
      //   store.commit('increase')
      // }, 1000)
    })
    // 暴露给template
    return {
      ...toRefs(state)
    }
  }
})
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
