<template>
	<main>
		<TemplateRef></TemplateRef>
		<hr />
		<TemplateChildRef ref="child"></TemplateChildRef>
	</main>
</template>

<script>
import TemplateRef from './TemplateRef.vue';
import TemplateChildRef from './TemplateChildRef.vue';
import { onMounted, ref } from 'vue';
export default {
	components: { TemplateRef, TemplateChildRef },
	setup() {
		const child = ref(null);
		const message = 'Parent message';
		onMounted(() => {
			console.log('child message : ', child.value.message);
			child.value.sayHello();
		});
		return { child, message };
	},
};
</script>

<style lang="scss" scoped></style>
