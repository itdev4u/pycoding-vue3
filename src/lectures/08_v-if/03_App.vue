<template>
	<div>
		<h1 v-show="ok">Title입니다.</h1>
		<button v-on:click="ok = !ok">toggle</button>
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const ok = ref(true);

		return { ok };
	},
};
</script>

<style lang="scss" scoped></style>
