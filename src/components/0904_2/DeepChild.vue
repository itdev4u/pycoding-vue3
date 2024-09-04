<template>
  <div class="card">
    <div class="card-header">Deep Child Component</div>
    <div class="card-body">{{ staticMessage }} : {{ message }} : {{ count }}</div>
  </div>
</template>

<script>
import { inject } from 'vue'

export default {
  setup() {
    const staticMessage = inject('static-message', 'Default Message')
    const { message, updateMessage } = inject('message')
    updateMessage('!!!')
    // message.value += '???'
    const count = inject('count')
    return {
      staticMessage,
      message,
      count
    }
  }
}
</script>

<style lang="scss" scoped></style>
