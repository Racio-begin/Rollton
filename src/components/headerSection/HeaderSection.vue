<script setup lang="ts">
import HeaderLogo from './HeaderLogo.vue'
</script>

<template>
	<section class="header">
		<div class="header__container">
			<div class="header__logo-container">
				<HeaderLogo />
			</div>
			<div class="header__sunrise-container">
				<!-- <span class="header__sun"></span> -->
				<span class="header__sunrise"></span>
			</div>
		</div>
	</section>
</template>

<style lang="scss" scoped>
.header {
	width: 100%;
	height: 1000px;
	position: relative;
	z-index: -1;

	&__container {
		width: 100%;
		height: 100%;
		background-color: var(--red-main);
		display: flex;
		justify-content: center;
		// align-items: center;

		position: relative;
	}

	&__logo-container {
		margin-top: 63px;
	}

	&__sunrise-container {
		width: 1490px;
		height: 1490px;
		position: absolute;
		left: 50%;
		bottom: 0;
		transform: translate(-50%, 50%);
	}

	&__sun {
		display: block;
		width: 600px;
		height: 600px;
		border-radius: 50%;
		background-color: var(--yellow);
	}

	&__sunrise {
		display: block;
		width: 100%;
		height: 100%;
		border-radius: 50%;

		background: radial-gradient(
			rgba(251, 217, 39, 1) 0%,
			rgba(251, 217, 39, 0) 74%
		);
	}
}
</style>
