<template>
	<div>
		<p>author : {{ author }}</p>
		<p>title : {{ title }}</p>
	</div>
</template>

<script>
import { reactive, toRef, toRefs } from 'vue';
export default {
	setup() {
		const book = reactive({
			author: 'Vue Team',
			year: '2020',
			title: 'Vue 3 Guide',
			description: '당신은 이책을 읽어야 합니다.',
			price: '무료',
		});

		//const { author, title } = book;
		const { author, title } = toRefs(book);
		const author2 = toRef(book, 'author');

		return { author, title, book, author2 };
	},
};
</script>

<style lang="scss" scoped></style>
