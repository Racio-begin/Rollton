<template>
	<section class="slider section-l">
		<div class="container">
			<h2 class="slider__title title-red">История <span>Роллтон</span></h2>
		</div>
		<div class="slider__container">
			<swiper
				:slides-per-view="slidesPerView"
				:space-between="20"
				@swiper="onSwiper"
				@slideChange="onSlideChange"
				:breakpoints="breakpoints"
			>
				<swiper-slide
					v-for="slide in slides"
					:key="slide.id"
					@click="() => togglePopup()"
					:togglePopup
				>
					<SlideSection />
				</swiper-slide>
			</swiper>
		</div>
		<PopupSection
			v-if="popupTriggers.buttonTrigger"
			:togglePopup="() => togglePopup()"
			:isVisible="isVisible"
		/>
	</section>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { Swiper, SwiperSlide } from 'swiper/vue'
import type { Swiper as SwiperInstance } from 'swiper'
import 'swiper/css'

import SlideSection from './SlideSection.vue'

import PopupSection from '../popupSection/PopupSection.vue'

//* СЛАЙДЕР *//
const slides = [
	{ id: 1 },
	{ id: 2 },
	{ id: 3 },
	{ id: 4 },
	{ id: 5 },
	{ id: 6 },
]

const slidesPerView = ref(3.4)

const breakpoints = {
	0: {
		slidesPerView: 1.8,
		spaceBetween: 10,
	},
	350: {
		slidesPerView: 2.5,
		spaceBetween: 10,
	},
	500: {
		slidesPerView: 3.4,
		spaceBetween: 20,
	},
}

const onSwiper = (swiper: SwiperInstance) => {
	console.log(swiper)
}

const onSlideChange = () => {
	console.log('slide change')
}

//* ПОПАП *//
const popupTriggers = ref({ buttonTrigger: false })
const isVisible = ref(false)
const togglePopup = () => {
	popupTriggers.value.buttonTrigger = !popupTriggers.value.buttonTrigger
	isVisible.value = !isVisible.value
}
</script>

<style lang="scss" scoped>
@use '../../assets/_functions.scss' as functions;
@use '../../assets/_mixins.scss' as mixins;

.slider {
	background-color: var(--light-optional);
	padding: 150px 0 123px;

	&__title {
		margin-bottom: 85px;

		& span {
			color: var(--yellow);
		}
	}
}

.swiper {
	width: 100%;
	height: 100%;

	.swiper-slide {
		position: relative;

		&:nth-child(1) {
			margin-left: 70px;
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
		height: auto;
		padding: functions.calcVH(150) 0 functions.calcVH(123);

		&__title {
			margin-bottom: functions.calcVH(85);
		}
	}

	.swiper {
		.swiper-slide {
			&:nth-child(1) {
				margin-left: functions.calcVW(70);
			}
		}
	}
}

@media (max-width: 1280px) {
	.swiper {
		width: 100%;
		height: 100%;

		.swiper-slide {
			&:nth-child(1)::before,
			&:nth-child(2)::before,
			&:nth-child(3)::before,
			&:nth-child(4)::before,
			&:nth-child(5)::before {
				width: 250px;
				background-size: contain;
			}
		}
	}
}

@media (max-width: 1024px) and (min-height: 1024px) {
	.slider {
		padding: functions.calcVH(100) 0 functions.calcVH(80);
	}
}

@media (max-width: 1024px) {
	.swiper {
		.swiper-slide {
			&:nth-child(1) {
				margin-left: 0;
			}
		}
	}
}

@media (max-width: 480px) {
	.slider {
		padding: functions.calcVH(80) 0 functions.calcVH(60);
	}

	.swiper {
		.swiper-slide {
			&:nth-child(1)::before,
			&:nth-child(2)::before,
			&:nth-child(3)::before,
			&:nth-child(4)::before,
			&:nth-child(5)::before {
				width: 150px;
			}
		}
	}
}

@media (max-width: 350px) {
	.swiper {
		.swiper-slide {
			&::before {
				top: 36%;
				left: 50%;
			}

			&:nth-child(1)::before,
			&:nth-child(2)::before,
			&:nth-child(3)::before,
			&:nth-child(4)::before,
			&:nth-child(5)::before {
				width: 150px;
			}

			&:nth-child(1) {
				margin-left: 10px;
			}
		}
	}
}
</style>
