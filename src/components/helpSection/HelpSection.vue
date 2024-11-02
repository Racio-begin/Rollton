<template>
	<section class="help section-m">
		<div class="container">
			<div class="help__container">
				<div class="help__heart-image">
					<img
						class="help__heart-image_1"
						src="../../img/heart-1.svg"
						alt="Сердце, внутри руки держат тепло"
					/>
					<img
						class="help__heart-image_2"
						src="../../img/heart-2.svg"
						alt="Сердце, внутри руки держат тепло"
					/>
				</div>
				<div class="help__content">
					<h3 class="title-green">На помощь деткам</h3>
					<P class="subtitle">пожертвования детским домам</P>
				</div>
			</div>
		</div>
	</section>
</template>

<style lang="scss" scoped>
@use '../../assets/_mixins.scss' as mixins;
@use '../../assets/_functions.scss' as functions;

.help {
	background-color: var(--light-optional);

	&__container {
		display: flex;
		align-items: center;
		padding: 66px 0 0;
	}

	&__heart-image {
		width: 630px;
		aspect-ratio: 630/560; // 1.125

		margin: 66px 28px 0 0;
		position: relative;
		overflow: hidden;

		&_1,
		&_2 {
			display: block;
			position: absolute;
			left: 0;
			top: 0;
			width: 100%;
			height: 100%;
			animation-duration: 4s;
			animation-timing-function: ease-in-out;
			animation-iteration-count: infinite;
		}

		&_2 {
			animation-name: fade;
		}
	}

	&__content {
		margin-top: 90px;
		flex: 1;

		& h3 {
			margin-bottom: 20px;
		}
	}
}

@keyframes fade {
	0% {
		opacity: 0;
	}
	50% {
		opacity: 1;
	}
	100% {
		opacity: 0;
	}
}

@media (max-width: 1920px) {
	.help {
		&__container {
			padding: functions.calcVH(66) 0 0;
		}

		&__heart-image {
			margin: functions.calcVH(66) functions.calcVW(28) 0 0;
		}

		&__content {
			margin-top: functions.calcVH(90);

			& h2 {
				margin-bottom: functions.calcVH(20);
			}
		}
	}
}

@media (max-width: 1440px) {
	.help {
		&__heart-image {
			width: 580px;
			// aspect-ratio: 580/515;
		}
	}
}

@media (max-width: 1280px) {
	.help {
		&__container {
			padding: functions.calcVH(30) 0 0;
		}

		&__heart-image {
			width: 480px;
			// aspect-ratio: 540/480;
			margin: functions.calcVH(66) functions.calcVW(28) 0 0;
		}

		// &__content {
		// 	margin-top: functions.calcVH(90);

		// 	& h2 {
		// 		margin-bottom: functions.calcVH(20);
		// 	}
		// }
	}
}
</style>
