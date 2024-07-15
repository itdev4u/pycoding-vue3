<template>
	<div>
		<div class="text" v-bind:class="classObject">텍스트입니다.</div>
	</div>
</template>

<script>
import { computed } from '@vue/reactivity'
import { ref, reactive } from 'vue';
export default {
	setup () {
		const isActive = ref(true);
		const hasError = ref(false);

		const classObject = computed(()=> {
			return {
				active: true,
				'text-danger': false
			}
		});

	


		return {
			isActive,
			hasError,
			classObject
		}
	}
}
</script>

<style scoped>
.active {
	font-weight: 900;
}
.text-danger {
	color: red;
}
</style>