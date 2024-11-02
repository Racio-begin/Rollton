<script setup lang="ts">
import AwardLogo from './AwardLogo.vue'
</script>

<template>
	<section class="awards section-m">
		<div class="container">
			<div class="awards__container">
				<div class="awards__content">
					<h3 class="title-green">Получили <span>20 наград</span></h3>
					<p class="subtitle">в различных номинациях</p>
				</div>
				<!-- <div class="awards__logo-container"> -->
				<AwardLogo />
				<!-- </div> -->
			</div>
		</div>
	</section>
</template>

<style lang="scss" scoped>
@use '../../assets/_mixins.scss' as mixins;
@use '../../assets/_functions.scss' as functions;

.awards {
	background-color: var(--yellow);

	&__container {
		width: 100%;
		padding-top: 35px;
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

	&__logo-container {
		&::before {
			position: absolute;
			content: '';
			left: 0;
			top: 0;
			width: 100px;
			height: 20px;
			background-color: red;
		}
	}
}

@media (max-width: 1920px) {
	.awards {
		&__container {
			// padding-top: 35px;
			padding-top: functions.calcVH(35);
		}

		&__content {
			// max-width: 580px;
			& h3 {
				// margin-bottom: 20px;
				margin-bottom: functions.calcVH(20);
			}
		}
	}
}

// @media (max-width: 1366px) {
// 	.awards {
// 		&__container {
// 			padding-top: 80px;
// 		}
// 	}
// }
</style>
