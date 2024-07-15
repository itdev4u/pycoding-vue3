<template>
	<div></div>
</template>

<script>
export default {
	setup() {
		const message = ref('');

		watch(nessage, (newValue, oldValue) => {
			console.log('newValue ==> ', newValue);
			console.log('oldValue ==> ', oldValue);
		});

		return {
			message,
		};
	},
};
</script>

<style lang="scss" scoped></style>
