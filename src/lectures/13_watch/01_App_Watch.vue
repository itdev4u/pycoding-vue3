<template>
	<div>
		<input type="text" v-model="message" />
	</div>
</template>

<script>
import { ref, watch } from 'vue';
export default {
	setup() {
		const message = ref('');

		watch(message, (newValue, oldValue) => {
			console.log('newValue ==> ', newValue);
			console.log('oldValue ==> ', oldValue);
		});

		return {
			message,
		};
	},
};
</script>

<style scoped></style>
