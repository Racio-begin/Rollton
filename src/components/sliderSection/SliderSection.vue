<template>
	<section class="slider section-l">
		<div class="container">
			<h2 class="slider__title title-red">История <span>Роллтон</span></h2>
		</div>
		<div class="slider__container">
			<swiper
				:slides-per-view="3"
				:space-between="50"
				@swiper="onSwiper"
				@slideChange="onSlideChange"
			>
				<swiper-slide><SlideSection /></swiper-slide>
				<swiper-slide><SlideSection /></swiper-slide>
				<swiper-slide><SlideSection /></swiper-slide>
				<swiper-slide><SlideSection /></swiper-slide>
				<swiper-slide><SlideSection /></swiper-slide>
				<swiper-slide><SlideSection /></swiper-slide>

				...
			</swiper>
		</div>
	</section>
</template>

<script lang="ts" setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import type { Swiper as SwiperInstance } from 'swiper'
import 'swiper/css'

import SlideSection from './SlideSection.vue'

const onSwiper = (swiper: SwiperInstance) => {
	console.log(swiper)
}
const onSlideChange = () => {
	console.log('slide change')
}
</script>

<style lang="scss" scoped>
@use '../../assets/_functions.scss' as functions;
@use '../../assets/_mixins.scss' as mixins;

.slider {
	background-color: var(--light-optional);
	height: 1000px;
	padding: 150px 0 123px;

	&__title {
		margin-bottom: 85px;

		& span {
			color: var(--yellow);
		}
	}

	// &__container {
	// 	margin-left: 100px;
	// }
}

.swiper {
	width: 100%;
	height: 100%;

	.swiper-slide {
		position: relative;

		&:nth-child(1) {
			margin-left: 100px;
		}

		&::before {
			content: '';
			position: absolute;
			top: 40%;
			left: 60%;
			width: 100%;
			height: 100%;
			background-repeat: no-repeat;
		}

		&:nth-child(1)::before,
		&:nth-child(4)::before {
			background-image: url('../../img/noodles/noodles-1.svg');
		}

		&:nth-child(2)::before,
		&:nth-child(5)::before {
			background-image: url('../../img/noodles/noodles-2.svg');
		}

		&:nth-child(3)::before {
			background-image: url('../../img/noodles/noodles-3.svg');
		}
	}
}

.swiper-slide {
	display: flex;
	justify-content: center;
	align-items: center;
}

.swiper-slide img {
	display: block;
	width: 100%;
	height: 100%;
	object-fit: cover;
}

@media (max-width: 1920px) {
	.slider {
	}
}
</style>
