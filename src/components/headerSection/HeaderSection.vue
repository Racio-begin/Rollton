<script setup lang="ts">
import HeaderLogo from './HeaderLogo.vue'
import HeaderCollage from './HeaderCollage.vue'

// const collageImage = ref('../../img/collage.png')
</script>

<template>
	<header class="header">
		<div class="header__container">
			<div class="header__logo-container">
				<HeaderLogo />
			</div>
			<div class="header__sunrise-container">
				<span class="header__sunrise"></span>
			</div>
			<div class="header__collage-container">
				<HeaderCollage />
			</div>
		</div>
	</header>
</template>

<style lang="scss" scoped>
.header {
	width: 100%;
	height: 1000px;
	position: relative;
	// z-index: -1;
	overflow: hidden;

	&__container {
		width: 100%;
		height: 100%;
		background-color: var(--red-main);
		display: flex;
		justify-content: center;
		align-items: flex-end;

		// position: relative;
		// position: absolute;
	}

	&__logo-container {
		margin-top: 63px;
		z-index: 1;
		position: absolute;
		top: 0;
	}

	&__collage-container {
		z-index: 1;
	}

	&__sunrise-container {
		width: 2100px;
		height: 2100px;
		position: absolute;
		left: 50%;
		bottom: 0;
		transform: translate(-50%, 50%);
	}

	&__sunrise {
		display: block;
		width: 100%;
		height: 100%;
		border-radius: 50%;

		background: radial-gradient(
			rgba(251, 217, 39, 1) 0%,
			rgba(251, 217, 39, 1) 10%,
			rgba(251, 217, 39, 0) 70%
		);

		backdrop-filter: blur(100px);
	}
}
</style>
