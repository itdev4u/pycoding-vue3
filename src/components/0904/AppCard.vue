<template>
	<div class="card">
		<div v-if="$slots.header" class="card-header">
			<slot name="header" header-message="헤더메시지"></slot>
		</div>
		<div v-if="$slots.default" class="card-body">
			<slot></slot>
		</div>
		<div v-if="$slots.footer" class="card-footer text-body-secondary">
			<slot
				name="footer"
				helloMessage="안녕하세요"
				childMessage="childMessage"
			></slot>
		</div>
	</div>
</template>

<script>
export default {
	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
