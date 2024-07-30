<template>
	<div></div>
</template>

<script>
import { reactive, ref, watch } from 'vue';

export default {
	/* STEP 01 */

	setup() {
		const x = ref(0);
		const y = ref(0);
	
		// watch(
		// 	() => x.value + y.value,
		// 	sum => {
		// 		console.log('sum : ', sum);
		// 	}
		// );
	
		watch(
			() => x.value + y.value,
			(sum, oldValue) => {
				console.log('sum : ', sum);
				console.log('oldValue : ', oldValue);
			}
		);

		return { x, y }
	},
	
	/* STEP 02 */
	// setup() {
	// 	const x = ref(0);
	// 	const y = ref(0);

	// 	watch([x, y], ([newX, newY]) => {
	// 		console.log('x : ', newX, ' y : ', newY);
	// 	});

	// 	return {x, y }
	// }

	/* STEP 03 */
	/*
	setup() {
		const x = ref(0);
		const y = ref(0);

		const obj = reactive({
			count: 0,
		});
		console.log(typeof obj.count);
		// watch(
		// 	obj,
		// 	(newValue, oldValue) => {
		// 		console.log('newValue: ', newValue);
		// 	},
		// );	
		// obj.count 를 감지하고 싶은 경우	
		watch(
			() => obj.count,
			(newValue, oldValue) => {
				console.log('newValue: ', newValue);
			},
		);		

		return {x, y, obj }
	}
	*/
	/* STEP 04 */
	/*
	setup() {
		const person = reactive({
			name: '홍길동',
			age: 30,
			hobby: '운동',
			obj: {
				count: 0,
			},
		});

		watch(person, newValue => {
			console.log('newValue: ', newValue);
		});
		
		return { person } 
	}
	*/

};
</script>

<style lang="scss" scoped></style>