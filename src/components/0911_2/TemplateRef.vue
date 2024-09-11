<template>
	<div class="container py-4">
		<input ref="input" type="text" />
		<div>{{ input }}</div>
		<!--div>{{ input.value }}</!div--><!-- 새로 고침시 오류발생 -->
		<div v-if="input">{{ input.value }}</div>
		<div v-if="input">{{ $refs.input.value }}</div>
		<div>{{ $refs.input === input }}</div>
	</div>
</template>

<script>
import { onMounted, ref } from 'vue';

export default {
	components: {},
	setup() {
		const input = ref(null);

		onMounted(() => {
			input.value.value = 'Hello World!';
			input.value.focus();
		});

		return {
			input,
		};
	},
};
</script>
