<template>
	<div>
		<!-- inline에서 이벤트 객체를 전달할때는 $event를 사용 -->
		<button @click="printEventInfo('Hello', $event)">
			Inline event Handler
		</button>
		<hr />
		<input type="text" @keyup="onKeyupHandler" />
	</div>
</template>

<script>
export default {
	setup() {
		const printEventInfo = (message, event) => {
			console.log('message : ', message);
			console.log('event.target: ', event.target);
			console.log('event.target.tagName : ', event.target.tagName);
		};

		const onKeyupHandler = event => {
			console.log('event.key : ', event.key);
		};

		return {
			printEventInfo,
			onKeyupHandler,
		};
	},
};
</script>

<style lang="scss" scoped></style>
