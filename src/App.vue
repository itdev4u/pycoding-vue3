<template>
  <div>
    <TheNav></TheNav>
    <TheView></TheView>
  </div>
</template>

<script>
import TheNav from './lectures/15_component/TheNav.vue'
import TheView from './lectures/15_component/TheView.vue'
export default {
  components: {
    // Key와 값이 같은 경우 생략이 가능
    TheNav,
    TheView: TheView
  },
  setup() {
    return {}
  }
}
</script>

<style lang="scss" scoped></style>
