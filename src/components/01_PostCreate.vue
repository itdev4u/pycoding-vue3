<template>
	<div>
		<!-- Event 이벤트를 발생 -->
		<!--button class="btn btn-primary" @click="$emit('CreatePost')">button</button-->
		<!--button class="btn btn-primary" @click="$emit('CreatePost', 1, 2, 3, '김길동')">button</button-->
		<button class="btn btn-primary" @click="createPost">Button</button>
	</div>
</template>

<script>
export default {
	/*
  setup() {
    return {}
  }
  */
	/*
  setup(props, context) {
    const createPost = () => {
      context.emit('createPost', 1, 2, 3, '김길동')
    }
    return { createPost }
  }
  */
	setup(props, { emit }) {
		const createPost = () => {
			emit('createPost', 1, 2, 3, '김길동');
		};
		return { createPost };
	},
};
</script>

<style lang="scss" scoped></style>
