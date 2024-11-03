<script lang="ts" setup>
import MomentsStars from './MomentsStars.vue'
</script>

<template>
	<div class="planet-image">
		<img
			src="../../img/planet-with-shadow.svg"
			alt="Планета, обёрнутая лапшой"
		/>
		<span class="planet-image__sunrise"></span>
		<MomentsStars />
	</div>
</template>

<style lang="scss" scoped>
@use '../../assets/_mixins.scss' as mixins;
@use '../../assets/_functions.scss' as functions;

.planet-image {
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
	}
}
@media (max-width: 1920px) {
	.planet-image {
		margin-top: functions.calcVH(80);
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
		&__sunrise {
			width: 450px;
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
