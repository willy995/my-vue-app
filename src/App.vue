<script setup>
import { reactive, ref, watch, watchEffect } from 'vue'
// const msg = ref("你好mmm")
const msg = reactive({
  name: "你好mmm",
  age: 18
})

const counter = ref(0)
watch(() => ({ ...msg }), (newValue, oldValue) => {
  console.log(newValue, oldValue)
}, {
  immediate: true,
  deep: true
})

const watchStop = watchEffect(() => {
  console.log(msg.name)
  console.log(counter.value)
  if (counter.value > 2) {
    watchStop()
  }

})
</script>

<template>
  hello world!
  <router-view></router-view>

  <el-button @click="msg.name = '你好kkk'">默认</el-button>
  <el-button @click="counter++">+1</el-button>

  <div>{{ msg.name }}</div>
  <div>{{ counter }}</div>
</template>

<style scoped>
#app {
  width: 100%;
  height: 100%;
  overflow: hidden;
}
</style>
