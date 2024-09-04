<template>
	<div>
		<TheNav></TheNav>
		<TheView></TheView>
	</div>
</template>

<script>
import TheNav from '@/components/TheNav.vue';
import TheView from '@/components/0904_2/TheView.vue';
export default {
	components: {
		// Key와 값이 같은 경우 생략이 가능
		TheNav,
		TheView: TheView,
	},
	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
