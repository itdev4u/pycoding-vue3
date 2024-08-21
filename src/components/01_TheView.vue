<template>
  <main>
    <div class="container py-4">
      <!-- Event 01 자식에서 보낸 이벤트 받기-->
      <PostCreate @CreatePost="createPost"></PostCreate>
      <div class="row g-5">
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
import PostCreate from '@/components/PostCreate.vue'

import { reactive } from 'vue'
export default {
  components: {
    AppCard,
    PostCreate
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
    // Event 확인 : 파라미터
    /*
    const createPost = () => {
      console.log('createPost')
    }
    */
    /*
    const createPost = (a, b, c, d) => {
      console.log('createPost : ', a, b, c, d)
    }
      */
    const createPost = (newTitle) => {
      console.log('createPost : ')
      console.log(newTitle)
    }
    return { posts, createPost }
  }
}
</script>

<style lang="scss" scoped></style>
