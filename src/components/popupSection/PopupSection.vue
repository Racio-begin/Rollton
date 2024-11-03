<script lang="ts" setup>
import arrowImage from '../../img/arrow.svg'
</script>

<template>
	<div class="popup">
		<div class="popup__container">
			<button class="popup__close-button">
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
				<div class="popup__text-container">
					<p>
						«Роллтон» – это любимые продукты миллионов потребителей. А всё
						потому, что вкус и качество ароматной кудрявой лапши и неповторимого
						нежного пюре остаются неизменными на протяжении более, чем 20 лет.
					</p>
					<p>
						«Роллтон» объединяет всех, независимо от пола и возраста, и всегда
						выручает горячим обедом! Где бы вас не настиг голод: на работе, в
						поездке или дома, ваш сытный перекус — всегда под рукой.
					</p>
				</div>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
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
		height: calc(100% - 310px);
		border-radius: 50px;
		padding: 80px 100px 0;
		background-color: var(--light-optional);
		position: relative;
	}

	// &__content {

	// }

	&__title-container {
		margin-bottom: 94px;
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
		font-family: 'PTSans', sans-serif;
		max-width: 300px;
		font-size: 40px;
		line-height: 110%;
		// font-weight: 400;
		// color: var(--green-light-2);
	}

	&__text-container {
		max-width: 600px;
		font-family: 'PTSans', sans-serif;
		font-size: 30px;
		font-weight: 400;
		line-height: 110%;
		color: var(--gray);

		p:first-child {
			margin-bottom: 10px;
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
			transform: scale(1.2);

			svg path {
				transition: stroke 0.3s ease-in-out;
				stroke: var(--green-light-2);
			}
		}
	}
}
</style>
