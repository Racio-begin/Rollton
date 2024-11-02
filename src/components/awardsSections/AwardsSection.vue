<script setup lang="ts">
import AwardImage from './AwardImage.vue'
</script>

<template>
	<section class="awards section-m">
		<div class="container">
			<div class="awards__container">
				<div class="awards__content">
					<h3 class="title-green">Получили <span>20 наград</span></h3>
					<p class="subtitle">в различных номинациях</p>
				</div>
				<div class="awards__logo-container">
					<AwardImage />
				</div>
			</div>
		</div>
	</section>
</template>

<style lang="scss" scoped>
@use '../../assets/_mixins.scss' as mixins;
@use '../../assets/_functions.scss' as functions;

.awards {
	background-color: var(--yellow);
	overflow: hidden;

	&__container {
		width: 100%;
		padding-top: 35px;
		padding-bottom: 100px;
		display: flex;
		justify-content: space-between;
		align-items: center;
		position: relative;
	}

	&__content {
		max-width: 580px;
		flex: 1;
		& h3 {
			margin-bottom: 20px;
			& span {
				white-space: nowrap;
			}
		}
	}

	// &__logo-container {
	// }
}

@media (max-width: 1920px) {
	.awards {
		&__container {
			padding-top: functions.calcVH(35);
			padding-bottom: functions.calcVH(100);
		}

		&__content {
			& h3 {
				margin-bottom: functions.calcVH(20);
			}
		}
	}
}

@media (max-width: 1280px) {
	.awards {
		&__container {
			padding-top: functions.calcVH(30);
			padding-bottom: functions.calcVH(70);
		}
	}
}

@media (max-width: 480px) {
	.awards {
		&__container {
			display: flex;
			flex-direction: column-reverse;
		}

		&__content {
			text-align: center;
		}

		&__logo-container {
			margin-bottom: 30px;
		}
	}
}
</style>
