<template>
	<div class="card">
		<div class="card-body">
			<h5 class="card-title red">{{ title }}</h5>
			<p class="card-text">{{ contents }}</p>
			<a href="#" class="btn btn-primary">Go somewhere</a>
		</div>
	</div>
</template>

<script>
export default {
	props: ['title', 'contents'],
	setup() {
		return {};
	},
};
</script>

<style scoped>
.red {
	color: red;
}
</style>
