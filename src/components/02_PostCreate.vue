<template>
	<div>
		<input v-model="title" type="text" class="form-control" />
		<button class="btn btn-primary" @click="createPost">Button</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	emits: {
		createPost: newTitle => {
			//Validate 체크
			console.log('validate: ', newTitle);
			if (!newTitle) {
				return false;
			}
			return true;
		},
	},
	setup(props, { emit }) {
		const title = ref('');
		const createPost = () => {
			emit('createPost', title.value);
		};
		return { createPost, title };
	},
};
</script>

<style lang="scss" scoped></style>
