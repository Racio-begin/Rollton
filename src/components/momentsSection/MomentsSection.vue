<script lang="ts" setup>
import MomentsImage from './MomentsImage.vue'
</script>

<template>
	<section class="moments section-l">
		<div class="container">
			<div class="moments__container">
				<h2 class="moments__title-mob title-red">Теплые моменты с Роллтон</h2>
				<div class="moments__content">
					<div class="moments__text-container">
						<h2 class="moments__title title-red">Теплые моменты с Роллтон</h2>
						<h3 class="title-green">Продали <span>2 млн км</span> лапши</h3>
						<p class="subtitle">что равно 50-ти обхватам Земли</p>
					</div>
					<MomentsImage />
				</div>
			</div>
		</div>
	</section>
</template>

<style lang="scss" scoped>
@use '../../assets/_mixins.scss' as mixins;
@use '../../assets/_functions.scss' as functions;

.moments {
	background-color: var(--yellow);
	text-align: left;
	overflow: hidden;

	&__container {
		padding: 150px 0 120px;
	}

	&__content {
		display: flex;
		justify-content: space-between;
		position: relative;
	}

	&__text-container {
		h3 {
			max-width: 450px;
			margin-bottom: 20px;

			& span {
				white-space: nowrap;
			}
		}

		p {
			max-width: 380px;
		}
	}

	&__title {
		max-width: 550px;
		margin-bottom: 90px;
	}

	&__title-mob {
		display: none;
	}
}

@media (max-width: 1920px) {
	.moments {
		&__container {
			padding: functions.calcVH(150) 0 functions.calcVH(120);
		}

		&__text-container {
			h3 {
				margin-bottom: functions.calcVH(20);
			}
		}

		&__title {
			margin-bottom: functions.calcVH(90);
		}
	}
}

@media (max-width: 1024px) and (min-height: 1024px) {
	.moments {
		&__container {
			padding: functions.calcVH(100) 0 functions.calcVH(90);
		}

		&__title {
			margin-bottom: functions.calcVH(40);
		}
	}
}

@media (max-width: 480px) {
	.moments {
		&__container {
			padding: functions.calcVH(90) 0 functions.calcVH(70);
		}

		&__content {
			flex-direction: column-reverse;
		}

		&__text-container {
			text-align: center;
		}

		&__title {
			display: none;
		}

		&__title-mob {
			display: block;
			margin-bottom: 50px;
		}

		// h3 {
		// 	max-width: 450px;
		// 	margin-bottom: 20px;

		// 	& span {
		// 		white-space: nowrap;
		// 	}
		// }

		// p {
		// 	max-width: 380px;
		// }
	}
}
</style>
