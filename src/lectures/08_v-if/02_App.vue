<template>
	<div>
		<template v-if="visible">
			<h1>Title</h1>
			<p>Paragraph 1</p>
			<p>Paragraph 2</p>
		</template>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup () {
		const visible = ref(true);

		return { visible }
	}
}
</script>

<style lang="scss" scoped>

</style>