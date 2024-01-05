<script lang="ts" setup>

</script>

<template>
    <div class="__game">
		<img class="vp-img-0" src="/media/base/Backdrop.png" alt="Backdrop">
		<!-- Static objects -->
		<SouvContainer />
		<!-- Dynamic objects -->
	</div>
</template>

<style lang="scss" scoped>
.__game {
	position: relative;
	aspect-ratio: 4/3 !important;
	height: 100vmin;
	background-color: rgb(25,25,25);
	overflow: hidden;
	user-select: none;
}
</style>