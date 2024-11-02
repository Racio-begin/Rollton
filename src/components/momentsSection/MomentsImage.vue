<script lang="ts" setup>
import MomentsStars from './MomentsStars.vue'
</script>

<template>
	<div class="planet-image">
		<img
			src="../../img/planet-with-shadow.svg"
			alt="Планета, обёрнутая лапшой"
		/>
		<!-- <img src="../../img/planet.svg" alt="Планета, обёрнутая лапшой" /> -->
		<span class="planet-image__sunrise"></span>
		<!-- <span class="planet-image__red-circle"></span> -->
		<MomentsStars />
	</div>
</template>

<style lang="scss" scoped>
@use '../../assets/_mixins.scss' as mixins;
@use '../../assets/_functions.scss' as functions;

.planet-image {
	// width: 100%;
	// position: relative;
	margin-top: 80px;
	display: flex;
	justify-content: flex-end;

	& img:nth-child(1) {
		position: relative;
		z-index: 10;
	}

	&__sunrise {
		width: 1000px;
		aspect-ratio: 1/1;
		position: absolute;
		top: -100px;
		left: 500px;
		background: radial-gradient(
			rgb(255, 255, 255, 1) 0%,
			rgba(197, 170, 37, 0) 60%
		);
		z-index: 5;

		// backdrop-filter: blur(200px);
	}

	// &__red-circle {
	// 	width: 600px;
	// 	aspect-ratio: 1/1;
	// 	position: absolute;
	// 	top: 420px;
	// 	right: 270px;
	// 	border-radius: 50%;
	// 	transform: translate(50%, -50%);
	// 	background-color: var(--red-main);
	// 	z-index: 9;
	// }

	// &__stars {
	// 	width: 908px;
	// 	height: 813px;
	// 	position: absolute;
	// 	top: 47%;
	// 	left: 74%;
	// 	transform: translate(-50%, -50%);
	// 	z-index: 10;
	// }
}
@media (max-width: 1920px) {
	.planet-image {
		margin-top: functions.calcVH(80);
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

@media (max-width: 1440px) {
	.planet-image {
		&__sunrise {
			width: 800px;

			top: -120px;
			left: 320px;
		}
	}
}

@media (max-width: 1024px) {
	.planet-image {
		&__sunrise {
			width: 700px;

			top: -110px;
			left: 210px;
		}
	}
}

@media (max-width: 820px) {
	.planet-image {
		width: 80%;
		margin-top: functions.calcVH(40);
		// &__sunrise {
		// 	width: 600px;

		// 	top: -90px;
		// 	left: 160px;
		// }

		&__sunrise {
			width: 600px;
			top: -110px;
			left: 180px;
		}
	}
}
@media (max-width: 768px) {
	.planet-image {
		margin-top: 0;
		margin-bottom: 30px;
		// &__sunrise {
		// 	width: 600px;

		// 	top: -90px;
		// 	left: 160px;
		// }

		&__sunrise {
			width: 500px;
			top: -80px;
			left: 190px;
		}
	}
}

@media (max-width: 480px) {
	.planet-image {
		width: 100%;

		&__sunrise {
			width: 500px;
			top: -100px;
			left: -100px;
		}
	}
}

@media (max-width: 375px) {
	.planet-image {
		// width: 100%;

		&__sunrise {
			width: 450px;
			// top: -100px;
			// left: -100px;
		}
	}
}

@media (max-width: 350px) {
	.planet-image {
		width: 100%;

		&__sunrise {
			width: 400px;
			top: -100px;
			left: -100px;
		}
	}
}
</style>
