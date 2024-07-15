<template>
	<div>
		<div :style="styleObject">Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto autem dignissimos consequuntur nobis nostrum quis rerum nesciunt! Nesciunt iusto, blanditiis enim dignissimos laudantium, eligendi sit quidem at assumenda, illo temporibus!</div>
		<div :style="styleObject2">Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto autem dignissimos consequuntur nobis nostrum quis rerum nesciunt! Nesciunt iusto, blanditiis enim dignissimos laudantium, eligendi sit quidem at assumenda, illo temporibus!</div>
		<button v-on:click="fontSize--">-</button>
		<button v-on:click="fontSize++">+</button>
	</div>
</template>

<script>
import { computed, reactive, ref } from 'vue';

export default {
	setup () {
		const styleObject = reactive({
			color: 'red',
			fontSize: '13px',
		});

		const fontSize = ref(13);
		const styleObject2 = computed(() => {
			return  {
				color: 'red',
				//fontSize: '13px',
				fontSize: fontSize.value + 'px'
			}
		})

		return { styleObject, styleObject2, fontSize }
	}
}
</script>

<style lang="scss" scoped>

</style>