<template>
	<div>
		<div id="modifiers">
			<div @click.capture="clickDiv">
				Div 영역
				<p @click.self="clickP">	
					P 영역
					<span @click="clickSpan">
						SPAN 영역
					</span>
					<!--a href="https://naver.com" @click.prevent="clickA">a 영역</a-->
					<a href="https://naver.com" @click.prevent.stop="clickA">a 영역</a>
				</p>
			</div>
		</div>
		<button @click.once="clickOnce">Once</button>
	</div>
</template>

<script>
export default {
	setup () {
		const clickDiv = () => {
			console.log('clickDiv');
			//location.href='https://daum.net';
		};

		const clickP = () => {
			console.log('clickP');
		};

		// const clickSpan = (event) => {
		// 	console.log('clickSpan');
		// 	event.stopPropagation();
		// 	alert('조아요');
		// };

		const clickSpan = () => {
			console.log('clickSpan');
			//alert('조아요');
		};		

		const clickA = () => {
			alert('A click');
		};

		const clickOnce = () => {
			console.log('Once Click');
		};

		return {
			clickDiv,
			clickP,
			clickSpan,
			clickA,
			clickOnce
		}
	}
}
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