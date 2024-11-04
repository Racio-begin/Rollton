<script lang="ts" setup>
import { ref } from 'vue'

import arrowImage from '../../img/arrow.svg'
import rolltonImage from '../../img/products/big-rollton-1.png'
import greenImage from '../../img/decor-1.png'
import tomatoImage from '../../img/decor-2.png'

const isVisible = ref(true) // состояние видимости попапа

const handleClosePopup = () => {
	console.log('close popup')
	isVisible.value = false
}

const handleOverlayClick = (event: MouseEvent) => {
	const popupContainer = document.querySelector('.popup__container')
	if (popupContainer && !popupContainer.contains(event.target as Node)) {
		handleClosePopup()
	}
}
</script>

<template>
	<div class="popup" v-show="isVisible" @click="handleOverlayClick">
		<div class="popup__container">
			<button class="popup__close-button" @click="handleClosePopup">
				<svg
					width="57"
					height="57"
					viewBox="0 0 57 57"
					fill="none"
					xmlns="http://www.w3.org/2000/svg"
				>
					<path
						d="M44 44L13 13"
						stroke="var(--green-light)"
						stroke-width="10"
						stroke-linecap="round"
					/>
					<path
						d="M13 44L44 13"
						stroke="var(--green-light)"
						stroke-width="10"
						stroke-linecap="round"
					/>
				</svg>
			</button>
			<div class="popup__content">
				<div class="popup__title-container">
					<h3 class="popup__title">1999</h3>
					<img :src="arrowImage" alt="Желтая стрелка, направленная вправо" />
					<p class="popup__subtitle">Первая пачка вермишели</p>
				</div>
				<span class="popup__line"></span>
				<div class="popup__text-container">
					<p>
						«Роллтон» – это любимые продукты миллионов потребителей. А всё
						потому, что вкус и качество ароматной кудрявой лапши и неповторимого
						нежного пюре остаются неизменными на протяжении более, чем 20 лет.
					</p>
					<p>
						«Роллтон» объединяет всех, независимо от пола и возраста, и всегда
						выручает горячим обедом!
					</p>
					<p>
						Где бы вас не настиг голод: на работе, в поездке или дома, ваш
						сытный перекус — всегда под рукой.
					</p>
				</div>
			</div>
			<div class="popup__image-container">
				<img
					class="popup__image-container_rollton"
					:src="rolltonImage"
					alt="Упаковка лапши Роллтон с курицей"
				/>
				<img
					class="popup__image-container_green"
					:src="greenImage"
					alt="Листики зелени"
				/>
				<img
					class="popup__image-container_tomato"
					:src="tomatoImage"
					alt="Маленький томат"
				/>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
@use '../../assets/_functions.scss' as functions;
@use '../../assets/_mixins.scss' as mixins;

.popup {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: rgba(87, 160, 60, 0.8);
	z-index: 50;

	display: flex;
	justify-content: center;
	align-items: center;

	&__container {
		width: calc(100% - 600px);
		// height: calc(100% - 310px);
		height: calc(100% - 200px);
		border-radius: 50px;
		// padding: 80px 100px 0;
		padding: 80px 0 0 100px;
		background-color: var(--white);
		position: relative;
	}

	// &__content {

	// }

	&__title-container {
		margin-bottom: 40px;
		display: flex;
		align-items: center;

		& img {
			margin-right: 40px;
		}
	}

	&__title {
		margin-right: 28px;
		font-size: 100px;
		font-weight: 700;
		color: var(--yellow);
	}

	&__subtitle {
		font-family: 'PTSans-Narrow', sans-serif;
		max-width: 300px;
		font-size: 40px;
		line-height: 110%;
	}

	&__text-container {
		max-width: 600px;
		margin-top: 40px;
		font-family: 'PTSans-Narrow', sans-serif;
		// font-size: 30px;
		font-size: 25px;
		font-weight: 400;
		line-height: 110%;
		color: var(--gray);

		p:first-child {
			margin-bottom: 10px;
		}
	}

	&__line {
		display: block;
		width: 100%;
		height: 10px;
		background-color: var(--light-optional);
	}

	&__image-container {
		position: absolute;
		right: 0;
		bottom: 0;

		&_rollton {
			max-width: 600px;
			width: 100%;
			aspect-ratio: 1/1;
			// height: 100%;
		}

		&_green {
			position: absolute;
			top: 0;
			left: 0;
		}

		&_tomato {
			position: absolute;
			bottom: 20%;
			right: 10%;
		}
	}

	&__close-button {
		position: absolute;
		top: 60px;
		right: 60px;
		background-color: transparent;
		cursor: pointer;
		transition: transform 0.3s ease-in-out;

		&:hover {
			transform: scale(1.2) rotate(180deg) translateY(4px);

			svg path {
				transition: stroke 0.3s ease-in-out;
				stroke: var(--green-light-2);
			}
		}
	}
}

@media (max-width: 1920px) {
	.popup {
		// &__container {
		// 	width: calc(100% - 400px);
		// 	height: calc(100% - 200px);

		// 	padding: 80px 0 0 100px;
		// }

		&__title-container {
			margin-bottom: functions.calcVH(40);

			& img {
				margin-right: functions.calcVW(40);
			}
		}

		&__title {
			margin-right: functions.calcVW(28);
			@include mixins.adaptive-font(100, 50);
		}

		&__subtitle {
			@include mixins.adaptive-font(40, 20);
		}

		&__text-container {
			// max-width: 600px;
			margin-top: functions.calcVH(40);
			// font-size: 30px;
			@include mixins.adaptive-font(25, 12);

			p:first-child {
				margin-bottom: functions.calcVH(10);
			}
		}
	}
}

@media (max-width: 1440px) {
	.popup {
		&__container {
			width: calc(100% - 300px);
			height: calc(100% - 200px);

			padding: 80px 0 0 100px;
		}

		&__image-container {
			&_rollton {
				max-width: 420px;
			}

			&_tomato {
				right: 8%;
				bottom: 15%;
			}
		}

		&__text-container {
			max-width: 460px;
		}
	}
}

@media (max-width: 1280px) {
	.popup {
		&__container {
			// width: calc(100% - 300px);
			// height: calc(100% - 200px);

			padding: 60px 0 0 70px;
		}

		&__image-container {
			&_rollton {
				max-width: 300px;
			}

			&_tomato {
				right: 8%;
				bottom: 15%;
			}
		}

		&__text-container {
			max-width: 350px;
		}

		&__close-button {
			top: 30px;
			right: 30px;

			svg {
				width: 40px;
				height: 40px;
			}
		}
	}
}

@media (max-width: 1024px) and (min-height: 1024px) {
	.popup {
		&__container {
			// width: calc(100% - 300px);
			height: calc(100% - 600px);
		}

		&__subtitle {
			max-width: 200px;
		}

		&__title-container {
			// margin-bottom: 40px;
			// display: flex;
			// align-items: center;

			& img {
				// margin-right: 40px;
				width: 80px;
			}
		}

		&__image-container {
			&_rollton {
				max-width: 340px;
			}

			&_green {
				width: 110px;
			}

			&_tomato {
				width: 100px;
				right: 7%;
				bottom: 15%;
			}
		}

		&__text-container {
			max-width: 350px;
		}

		&__close-button {
			top: 30px;
			right: 30px;

			svg {
				width: 40px;
				height: 40px;
			}
		}
	}
}

@media (max-width: 820px) {
	.popup {
		&__container {
			width: calc(100% - 200px);
			height: calc(100% - 400px);
		}

		&__subtitle {
			max-width: 200px;
		}

		&__image-container {
			&_rollton {
				max-width: 340px;
			}

			&_green {
				width: 110px;
			}

			&_tomato {
				width: 100px;
				right: 7%;
				bottom: 15%;
			}
		}

		&__text-container {
			max-width: 400px;
			font-size: 16px;
		}
	}
}

@media (max-width: 768px) {
	.popup {
		&__container {
			height: calc(100% - 300px);
		}
	}
}
</style>
