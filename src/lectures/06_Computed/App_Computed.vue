<template>
	<div>
		<h2>{{ teacher.name }}</h2>
		<h3>강의가 있습니까?</h3>
		<p>javascript : {{ teacher.leactures.length > 0 ? '있음' : '없음' }}</p>
		<p>computed : {{ haslecture }}</p>
		<p>method : {{ existlecture() }}</p>
		<!--
    <p>computed : {{ haslecture }}</p>
    <p>method : {{ existlecture() }}</p>
    <p>computed : {{ haslecture }}</p>
    <p>method : {{ existlecture() }}</p>
    <p>computed : {{ haslecture }}</p>
    <p>method : {{ existlecture() }}</p>
		-->
		<button v-on:click="counter++">Counter : {{ counter }}</button>
		<h2>이름</h2>
		<p>{{ fullName }}</p>
	</div>
</template>

<script>
import { reactive, computed, ref } from 'vue';

export default {
	setup() {
		const teacher = reactive({
			name: 'pycoding',
			leactures: ['HTML/CSS', 'JAVA', 'Vue', 'Unity'],
		});

		const haslecture = computed(() => {
			console.log('computed');
			return teacher.leactures.length > 0 ? '있음' : '없음';
		});

		const existlecture = () => {
			console.log('method');
			return teacher.leactures.length > 0 ? '있음' : '없음';
		};

		const counter = ref(0);

		const firstName = ref('홍');
		const lastName = ref('길동');
		/*
    const fullName = computed(() => {
      return firstName.value + ' ' + lastName.value
    })
		*/
		const fullName = computed({
			get() {
				return firstName.value + ' ' + lastName.value;
			},
			set(value) {
				[firstName.value, lastName.value] = value.split(' ');
			},
		});
		console.log('before fullane : ', fullName.value);
		fullName.value = '파이 코딩';
		console.log('after fullane : ', fullName.value);

		return { teacher, haslecture, existlecture, counter, fullName };
	},
};
</script>

<style lang="scss" scoped></style>
