<script setup lang="ts">
import AwardLogo from './AwardLogo.vue'
</script>

<template>
	<section class="awards">
		<div class="container">
			<div class="awards__container">
				<div class="awards__content">
					<h3 class="title-green">Получили <span>20 наград</span></h3>
					<p class="subtitle">в различных номинациях</p>
				</div>
				<AwardLogo />
			</div>
		</div>
	</section>
</template>

<style lang="scss" scoped>
.awards {
	width: 100%;
	height: 800px;
	background-color: var(--yellow);

	&__container {
		width: 100%;
		padding-top: 35px;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	&__content {
		max-width: 580px;
		& h3 {
			margin-bottom: 20px;
			& span {
				white-space: nowrap;
			}
		}
	}
}
</style>
