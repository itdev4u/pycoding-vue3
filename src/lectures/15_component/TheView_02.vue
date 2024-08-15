<template>
  <main>
    <!-- 07. Card 최상위 띄우기 -->
    <div class="container py-4">
      <!-- 06. Gutters 값울 조절 gx-5 / gy-5 / g-5-->
      <div class="row g-5">
        <!-- 05. 한줄에 3개씩 배치 -->
        <div class="col col-4"><AppCard></AppCard></div>
        <div class="col col-4"><app-card></app-card></div>
        <div class="col col-4"><AppCard></AppCard></div>
        <div class="col col-4"><AppCard></AppCard></div>
        <div class="col col-4"><AppCard></AppCard></div>
        <div class="col col-4"><AppCard></AppCard></div>
      </div>
    </div>
  </main>
</template>

<script>
import AppCard from './AppCard.vue'
export default {
  components: {
    AppCard
  },
  setup() {
    return {}
  }
}
</script>

<style lang="scss" scoped></style>
