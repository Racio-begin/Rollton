<template>
	<div class="planet-image">
		<img src="../../img/planet.svg" alt="Планета, обёрнутая лапшой" />
		<span class="planet-image__sunrise"></span>
		<span class="planet-image__red-circle"></span>
		<img
			src="../../img/stars.svg"
			alt="Звезды вокруг планеты"
			class="planet-image__stars"
		/>
	</div>
</template>

<style lang="scss" scoped>
.planet-image {
	// width: 100%;
	// position: relative;
	display: flex;
	justify-content: flex-end;

	& img:nth-child(1) {
		position: relative;
		z-index: 10;
	}

	&__sunrise {
		width: 1000px;
		height: 1000px;
		position: absolute;
		top: -100px;
		left: 500px;
		background: radial-gradient(
			rgb(255, 255, 255, 1) 0%,
			rgba(197, 170, 37, 0) 60%
		);
		z-index: 5;

		backdrop-filter: blur(200px);
	}

	&__red-circle {
		width: 602px;
		height: 602px;
		position: absolute;
		top: 420px;
		right: 270px;
		border-radius: 50%;
		transform: translate(50%, -50%);
		background-color: var(--red-main);
		z-index: 9;
	}

	&__stars {
		width: 908px;
		height: 813px;
		position: absolute;
		top: 48%;
		left: 75%;
		transform: translate(-50%, -50%);
		z-index: 15;
	}
}
@media (max-width: 1920px) {
	.planet-image {
		// &__sunrise {
		// 	width: 1000px;
		// 	height: 1000px;

		// 	top: -50px;
		// 	left: 400px;
		// }

		// &__red-circle {
		// width: 602px;
		// height: 602px;

		// top: 420px;
		// right: 270px;
		// }

		// &__stars {
		// width: 908px;
		// height: 813px;

		// top: 48%;
		// left: 75%;
		// }
	}
}
</style>
