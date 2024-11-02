<script lang="ts" setup>
import MomentsImage from './MomentsImage.vue'
</script>

<template>
	<section class="moments section-l">
		<div class="container">
			<div class="moments__container">
				<div class="moments__content">
					<div class="moments__text-container">
						<h2 class="moments__title title-red">Теплые моменты с Роллтон</h2>
						<h3 class="title-green">Продали 2 млн км лапши</h3>
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
		h2 {
			max-width: 550px;
			margin-bottom: 90px;
		}

		h3 {
			max-width: 450px;
			margin-bottom: 20px;
		}

		p {
			max-width: 380px;
		}
	}
}

@media (max-width: 1920px) {
	.moments {
		&__container {
			padding: functions.calcVH(150) 0 functions.calcVH(120);
		}

		&__text-container {
			h2 {
				margin-bottom: functions.calcVH(90);
			}

			h3 {
				margin-bottom: functions.calcVH(20);
			}
		}
	}
}
</style>
