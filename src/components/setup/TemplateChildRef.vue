// Child.vue
<template>
  <div class="container py-4">
    Child Component
    <div>parent mag ==> {{ $parent.msg }}</div>
  </div>
</template>
<script setup>
import { onMounted, ref } from 'vue'
const message = ref('Hello Child!')
defineExpose({
  message
})
</script>

<style lang="scss" scoped></style>
