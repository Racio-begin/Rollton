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
		padding-top: 110px;
		padding-bottom: 130px;
	}

	&__heart-image {
		width: 630px;
		aspect-ratio: 630/560; // 1.125

		margin-right: 28px;
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
			padding-top: functions.calcVH(110);
			padding-bottom: functions.calcVH(130);
		}

		&__heart-image {
			margin-right: functions.calcVW(28);
		}

		&__content {
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
		}
	}
}

@media (max-width: 1280px) {
	.help {
		&__container {
			padding-top: functions.calcVH(60);
			padding-bottom: functions.calcVH(80);
		}

		&__heart-image {
			width: 480px;
			margin-right: functions.calcVW(25);
		}
	}
}

@media (max-width: 820px) {
	.help {
		&__heart-image {
			width: 380px;
		}
	}
}

@media (max-width: 768px) {
	.help {
		&__heart-image {
			width: 350px;
		}
	}
}

@media (max-width: 480px) {
	.help {
		&__container {
			display: flex;
			flex-direction: column;
		}

		&__heart-image {
			margin-bottom: 30px;
		}

		&__content {
			text-align: center;
		}
	}
}

@media (max-width: 350px) {
	.help {
		&__heart-image {
			width: 300px;
		}
	}
}
</style>
