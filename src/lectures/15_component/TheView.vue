<template>
  <main>
    <!-- 07. Card 최상위 띄우기 -->
    <div class="container py-4">
      <!-- 06. Gutters 값울 조절 gx-5 / gy-5 / g-5-->
      <div class="row g-5">
        <!-- 05. 한줄에 3개씩 배치 -->
        <div v-for="post in posts" :key="post.id" class="col col-4">
          <AppCard
            :type="post.type"
            :title="post.title"
            :contents="post.contents"
            :isLike="post.isLike"
          ></AppCard>
          <!-- 04. 이벤트의 방향성 -->
          <!--button @click="post.isLike = !post.isLike">toggle</button-->
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import AppCard from './AppCard.vue'
import { reactive } from 'vue'
export default {
  components: {
    AppCard
  },
  setup() {
    const posts = reactive([
      { id: 1, type: 'notice', title: '제목1', contents: '내용1', isLike: true },
      { id: 2, title: '제목2', contents: '내용2' },
      { id: 3, title: '제목3', contents: '내용3' },
      { id: 4, title: '제목4', contents: '내용4' },
      { id: 5, title: '제목5', contents: '내용5' },
      { id: 6, title: '제목6', contents: '내용6' }
    ])
    return { posts }
  }
}
</script>

<style lang="scss" scoped></style>
