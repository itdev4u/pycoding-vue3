<template>
  <div>
    {{ msg }}
    <button @click="sayHello">Hello</button>
    <input v-model="message" type="text" />
    {{ message }}
  </div>
  <div>
    <PostItem type="news" title="제목" contents="내용" :isLike="true"></PostItem>
    <hr />
    <TemplateChildRef ref="child"></TemplateChildRef>
    <template v-if="child">{{ child.message }}</template>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import PostItem from './PostItem.vue'
import TemplateChildRef from './TemplateChildRef.vue'

const message = ref('')
const msg = 'Hello World!!'
const sayHello = () => {
  alert('Hello World')
}

const child = ref(null)
defineExpose({
  msg
})
</script>

<style lang="scss" scoped></style>
