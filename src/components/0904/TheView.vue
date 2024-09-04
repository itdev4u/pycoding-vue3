<template>
	<main>
		<div>
			<FancyButton>
				Click!!! <span style="color: red">@@@</span></FancyButton
			>
			<FancyButton v-slot="{ fancyMessage }">{{
				fancyMessage
			}}</FancyButton>
			<hr />
			<AppCard>
				<template #header="{ headerMessage }"
					>제목입니다. : {{ headerMessage }}</template
				>
				<template v-slot:default>내용입니다.</template>
				<template #footer="{ helloMessage, childMessage }"
					>푸터입니다. : {{ helloMessage }} :
					{{ childMessage }}</template
				>
			</AppCard>
			<hr />
			<AppCard>
				<template v-slot:default>디폴터만 사용하고 싶어</template>
			</AppCard>
		</div>
	</main>
</template>

<script>
import FancyButton from './FancyButton.vue';
import AppCard from './AppCard.vue';

export default {
	components: {
		FancyButton,
		AppCard,
	},

	setup() {
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
