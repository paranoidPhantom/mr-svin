<script lang="ts" setup>
const game_loop_stage = useState<number>("game_loop", () => 0)
const shake_state = ref(false)
const action_shake = () => {
	game_loop_stage.value = 1
	let count = 0
	const shake_interval = setInterval(() => {
		count++
		if (count > 15) {
			clearInterval(shake_interval)
			game_loop_stage.value = 2
			return
		}
		shake_state.value = !shake_state.value
	}, 100)
}
</script>

<template>
	<div class="_souv-container">
		<div v-if="game_loop_stage === 0" @click="action_shake" class="hitbox hb vid"></div>
		<img class="vp-img-0" v-show="shake_state" src="/media/souv-container/Shake.png" alt="Shake">
		<img class="vp-img-0" v-show="!shake_state" src="/media/souv-container/Default.png" alt="Default">
	</div>
</template>

<style lang="scss" scoped>
.hitbox {
	top: 52%;
	width: 15%;
	height: 20%;
	cursor: pointer;
	rotate: 65deg;
}
</style>