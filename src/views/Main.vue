
<template>
  <div @click="divClick">main 组件</div>
</template>

<script setup>
const divClick = (e) => {
  console.log("-----", e)
};
</script>

<style scoped></style>
