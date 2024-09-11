<template>
  <div class="container py-4">
    <div>Setup1 TheView</div>
    <div>
      <ScriptSetup></ScriptSetup>
    </div>
  </div>
</template>

<script>
import ScriptSetup from './ScriptSetup.vue'
export default {
  components: {
    ScriptSetup
  },
  setup() {
    return {}
  }
}
</script>
<!--script setup>
import ScriptSetup from './ScriptSetup.vue'
</script-->

<style lang="scss" scoped></style>
