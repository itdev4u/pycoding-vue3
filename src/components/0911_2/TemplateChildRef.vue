// Child.vue
<template>
	<div class="container py-4">
		Child Component
		<div>{{ $parent.message }}</div>
	</div>
</template>
<script>
import { onMounted, ref } from 'vue';

export default {
	setup() {
		const message = ref('Hello Child!');
		const sayHello = () => {
			alert(message.value);
		};

		return {
			message,
			sayHello,
		};
	},
};
</script>

<style lang="scss" scoped></style>
