<template>
	<div>
		<div id="modifiers">
			<div @click="clickDiv">
				Div 영역
				<p @click="clickP">
					P 영역
					<span @click="clickSpan"> SPAN 영역 </span>
					<a href="https://naver.com" @click="clickA">a 영역</a>
				</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	setup() {
		const clickDiv = () => {
			console.log('clickDiv');
		};

		const clickP = () => {
			console.log('clickP');
		};

		const clickSpan = () => {
			console.log('clickSpan');
		};

		const clickA = () => {
			alert('A click');
		};

		return {
			clickDiv,
			clickP,
			clickSpan,
			clickA,
		};
	},
};
</script>

<style scoped>
#modifiers div,
#modifiers p,
#modifiers span {
	padding: 40px;
}

#modifiers div {
	background-color: #ccc;
}

#modifiers p {
	background-color: #999;
}

#modifiers span {
	background-color: #666;
	display: block;
}
</style>
