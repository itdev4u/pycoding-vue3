<template>
  <div class="card">
    <div class="card-body">
      <!-- 01. type : news, notice에 따라 뉴스 또는 공지사항 -->
      <span class="badge text-bg-secondary">{{ type === 'news' ? '뉴스' : '공지사항' }}</span>
      <span class="badge text-bg-secondary">{{ typeName }}</span>
      <h5 class="card-title red mt-2">{{ title }}</h5>
      <p class="card-text">{{ contents }}</p>
      <!-- 02. isLike 좋아요 색상바꾸기 -->
      <!--a v-if="isLike" href="#" class="btn btn-danger">좋아요</a>
      <a-- v-else href="#" class="btn btn-outline-danger">좋아요</a-->
      <!-- 03. isLike 한줄로 만들기 -->
      <a href="#" class="btn" :class="isLikeClass" @click="toggleLike">좋아요</a>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue'
export default {
  /*
  props: ['title', 'contents'],
  setup() {
    return {}
  }
  */
  props: {
    //type에 validate 속성으로 news / notice만 받아야 함
    type: {
      type: String,
      default: 'news',
      validate: (value) => {
        return ['news', 'notice'].includes(value)
      }
    },
    title: {
      type: String,
      required: true
    },
    contents: {
      type: String,
      required: true
    },
    isLike: {
      type: Boolean,
      default: false
    }
  },
  setup(props) {
    console.log('props.title: ', props.title)
    const isLikeClass = computed(() => (props.isLike ? 'btn-danger' : 'btn-outline-danger'))
    const typeName = computed(() => (props.type === 'news' ? '뉴스' : '공지사항'))
    const toggleLike = () => {
      props.isLike = !props.isLike
    }
    return { isLikeClass, typeName, toggleLike }
  }
}
</script>

<style scoped>
.red {
  color: red;
}
</style>
