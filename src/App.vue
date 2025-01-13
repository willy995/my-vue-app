<script setup>
import { reactive, ref, watch } from 'vue'
// const msg = ref("你好mmm")
const msg = reactive({
  name: "你好mmm",
  age: 18
})
watch(() => ({ ...msg }), (newValue, oldValue) => {
  console.log(newValue, oldValue)
}, {
  immediate: true,
  deep: true
})
</script>

<template>
  hello world!
  <router-view></router-view>

  <el-button @click="msg.name = '你好kkk'">默认</el-button>

  <div>{{ msg.name }}</div>
</template>

<style scoped>
#app {
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>
