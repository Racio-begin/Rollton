<template>
	<section class="help">
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
.help {
	width: 100%;
	height: 800px;
	background-color: var(--light-optional);

	&__container {
		display: flex;
		padding: 66px 0;
	}

	&__heart-image {
		width: 628px;
		height: 560px;
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
		margin-top: 232px;
		flex: 1;

		& h2 {
			margin-bottom: 20px;
		}

		& p {
			font-size: 29px;
			line-height: 110%;
			font-weight: 500;
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
			padding: caclVH(66) 0;
		}

		&__heart-image {
			margin: calcVH(66) calcVW(28) 0 0;
		}

		&__content {
			margin-top: calcVH(232);

			& h2 {
				margin-bottom: calcVH(20);
			}
		}
	}
}
</style>
