<template>
	<div class="container py-4">
		<div class="card">
			<div class="card-header">Provide Inject Component</div>
			<div class="card-body">
				<button @click="count++">click</button>
				<Child></Child>
			</div>
		</div>
	</div>
</template>

<script>
import { provide, readonly, ref } from 'vue';
import Child from './Child.vue';
export default {
	components: {
		Child,
	},
	setup() {
		const staticMessage = 'static message';
		const message = ref('message');
		const updateMessage = appendMessage => {
			message.value = message.value + appendMessage;
		};
		const count = ref(10);
		provide('static-message', staticMessage);
		provide('message', { message: readonly(message), updateMessage });
		provide('count', count);

		return { count };
	},
};
</script>

<style lang="scss" scoped></style>
