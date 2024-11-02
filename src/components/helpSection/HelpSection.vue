<script lang="ts" setup>
import HelpImage from './HelpImage.vue'
</script>

<template>
	<section class="help section-m">
		<div class="container">
			<div class="help__container">
				<HelpImage />
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

	&__content {
		flex: 1;

		& h3 {
			margin-bottom: 20px;
		}
	}
}

@media (max-width: 1920px) {
	.help {
		&__container {
			padding-top: functions.calcVH(110);
			padding-bottom: functions.calcVH(130);
		}

		&__content {
			& h2 {
				margin-bottom: functions.calcVH(20);
			}
		}
	}
}

@media (max-width: 1280px) {
	.help {
		&__container {
			padding-top: functions.calcVH(60);
			padding-bottom: functions.calcVH(80);
		}
	}
}

@media (max-width: 480px) {
	.help {
		&__container {
			display: flex;
			flex-direction: column;
		}

		&__content {
			text-align: center;
		}
	}
}
</style>
