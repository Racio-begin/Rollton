<template>
	<section class="moments">
		<div class="container">
			<div class="moments__container">
				<div class="moments__content">
					<div class="moments__text-container">
						<h2 class="moments__title title-red">Теплые моменты с Роллтон</h2>
						<h3 class="title-green">Продали 2 млн км лапши</h3>
						<p class="subtitle">что равно 50-ти обхватам Земли</p>
					</div>
					<div class="moments__image-container">
						<img src="../../img/planet.svg" alt="Планета, обёрнутая лапшой" />
						<span class="moments__sunrise"></span>
						<span class="moments__red-circle"></span>
						<img
							src="../../img/stars.svg"
							alt="Звезды вокруг планеты"
							class="moments__stars"
						/>
					</div>
				</div>
			</div>
		</div>
	</section>
</template>

<style lang="scss" scoped>
@use '../../assets/_mixins.scss' as mixins;
@use '../../assets/_functions.scss';

.moments {
	width: 100%;
	height: 1000px;
	background-color: var(--yellow);
	text-align: left;
	overflow: hidden;

	&__container {
		padding: 150px 0 0;
	}

	&__content {
		display: flex;
		justify-content: space-between;
		position: relative;
	}

	&__text-container {
		position: absolute;
		left: 0;
		top: 0;

		p:nth-of-type(1) {
			max-width: 450px;
			margin-bottom: 20px;
			font-size: 80px;
			line-height: 110%;
			font-weight: 700;
			color: var(--green-light);
			text-transform: uppercase;
		}

		p:nth-of-type(2) {
			max-width: 380px;
		}
	}

	&__title {
		max-width: 550px;
		margin-bottom: 90px;
	}

	&__image-container {
		width: 100%;
		position: relative;
		display: flex;
		justify-content: flex-end;

		& img:nth-child(1) {
			position: relative;
			z-index: 10;
		}
	}

	&__sunrise {
		width: 1000px;
		height: 1000px;
		position: absolute;
		top: -50px;
		left: 400px;
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

	@media (max-width: 1920px) {
		.moments {
			&__container {
				padding: calcVH(150) 0 0;
			}
		}

		&__text-container {
			p:nth-of-type(1) {
				// max-width: 450px;
				// margin-bottom: 20px;
				margin-bottom: calcVH(20);
				// font-size: 80px;
				@include mixins.adaptive-font(80, 40);
				// line-height: 110%;
				// font-weight: 700;
				// color: var(--green-light);
				// text-transform: uppercase;
			}

			p:nth-of-type(2) {
				// max-width: 380px;
				font-size: 29px;
				@include mixins.adaptive-font(29, 16);
				// line-height: 110%;
				// font-weight: 500;
			}
		}

		&__title {
			// max-width: 550px;
			// margin-bottom: 90px;
			margin-bottom: calcVH(90);
			font-size: 50px;
			@include mixins.adaptive-font(50, 26);
			// line-height: 110%;
			// font-weight: 700;
			// color: var(--red-main);
			// text-transform: uppercase;
		}

		&__sunrise {
			width: 1000px;
			height: 1000px;

			top: -50px;
			left: 400px;
		}

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
