<script setup lang="ts">
import { ref } from 'vue'
import HeaderLogo from './HeaderLogo.vue'
import HeaderCollage from './HeaderCollage.vue'

import AnniversaryImage from '../../img/anniversary.png'

// Переменные состояния
const imageSwitched = ref(false)
const logoAnimated = ref(false)
const anniversaryAnimated = ref(false)

// Функция для переключения изображения при клике
const toggleImage = () => {
	imageSwitched.value = true
	logoAnimated.value = true
	anniversaryAnimated.value = true
	console.log('ПроверОчка', logoAnimated.value)
}
</script>

<template>
	<header class="header section-l">
		<div class="header__container">
			<div :class="['header__logo-container', { animated: logoAnimated }]">
				<HeaderLogo />
			</div>
			<div class="header__sunrise-container">
				<span class="header__sunrise"></span>
			</div>
			<div class="header__collage-container">
				<HeaderCollage
					@toggle-image="toggleImage"
					:imageSwitched="imageSwitched"
				/>
			</div>
			<div
				:class="[
					'header__anniversary-container',
					{ animated: anniversaryAnimated },
				]"
			>
				<img :src="AnniversaryImage" alt="Надпись - 25 лет дарим тепло" />
			</div>
		</div>
	</header>
</template>

<style lang="scss" scoped>
.header {
	position: relative;
	overflow: hidden;

	&__container {
		width: 100%;
		height: 100%;
		background-color: var(--red-main);
		display: flex;
		justify-content: center;
		align-items: flex-end;
	}

	&__logo-container {
		margin-top: 63px;
		z-index: 1;
		position: absolute;
		top: 0;
		transition: all 0.5s ease-in-out;

		&.animated {
			left: 25%;
			top: 4%;
			transform: translate(-50%, -50%) scale(0.19);
		}
	}

	&__collage-container {
		width: 100%;
		height: 1000px;
		display: flex;
		justify-content: center;
		align-items: center;
		z-index: 1;
	}

	&__sunrise-container {
		width: 2100px;
		// height: 2100px;
		aspect-ratio: 1/1;
		position: absolute;
		left: 50%;
		bottom: 0;
		transform: translate(-50%, 50%);
	}

	&__sunrise {
		display: block;
		width: 100%;
		height: 100%;
		border-radius: 50%;

		background: radial-gradient(
			rgba(251, 217, 39, 1) 0%,
			rgba(251, 217, 39, 1) 10%,
			rgba(251, 217, 39, 0) 70%
		);

		backdrop-filter: blur(100px);
	}

	&__anniversary-container {
		position: absolute;
		left: 50%;
		top: 50%;
		opacity: 0;
		transform: translate(-40%, -45%);

		transition: all 0.8s ease-in-out;
		transition-delay: 0.5s;
		pointer-events: none;
		z-index: 4;

		&.animated {
			opacity: 1;
			transform: translate(-40%, -65%);
		}
	}
}

@media (max-width: 1440px) {
	.header {
		// &__container {
		// 	width: 100%;
		// 	height: 100%;
		// 	background-color: var(--red-main);
		// 	display: flex;
		// 	justify-content: center;
		// 	align-items: flex-end;
		// }

		// &__logo-container {
		// 	margin-top: 63px;
		// 	z-index: 1;
		// 	position: absolute;
		// 	top: 0;
		// 	transition: all 0.5s ease-in-out;

		// 	&.animated {
		// 		left: 25%;
		// 		top: 4%;
		// 		transform: translate(-50%, -50%) scale(0.19);
		// 	}
		// }

		&__collage-container {
			width: 70%;
			height: 900px;
		}

		// &__sunrise-container {
		// 	width: 2100px;
		// 	height: 2100px;
		// 	position: absolute;
		// 	left: 50%;
		// 	bottom: 0;
		// 	transform: translate(-50%, 50%);
		// }

		// &__sunrise {
		// 	display: block;
		// 	width: 100%;
		// 	height: 100%;
		// 	border-radius: 50%;

		// 	background: radial-gradient(
		// 		rgba(251, 217, 39, 1) 0%,
		// 		rgba(251, 217, 39, 1) 10%,
		// 		rgba(251, 217, 39, 0) 70%
		// 	);

		// 	backdrop-filter: blur(100px);
		// }

		// &__anniversary-container {
		// 	position: absolute;
		// 	left: 50%;
		// 	top: 50%;
		// 	opacity: 0;
		// 	transform: translate(-40%, -45%);

		// 	transition: all 0.8s ease-in-out;
		// 	transition-delay: 0.5s;
		// 	pointer-events: none;
		// 	z-index: 4;

		// 	&.animated {
		// 		opacity: 1;
		// 		transform: translate(-40%, -65%);
		// 	}
		// }
	}
}

@media (max-width: 1366px) {
	.header {
		// &__container {
		// 	width: 100%;
		// 	height: 100%;
		// 	background-color: var(--red-main);
		// 	display: flex;
		// 	justify-content: center;
		// 	align-items: flex-end;
		// }

		// &__logo-container {
		// 	margin-top: 63px;
		// 	z-index: 1;
		// 	position: absolute;
		// 	top: 0;
		// 	transition: all 0.5s ease-in-out;

		// 	&.animated {
		// 		left: 25%;
		// 		top: 4%;
		// 		transform: translate(-50%, -50%) scale(0.19);
		// 	}
		// }

		&__collage-container {
			width: 60%;
			height: 800px;
		}

		// &__sunrise-container {
		// 	width: 2100px;
		// 	height: 2100px;
		// 	position: absolute;
		// 	left: 50%;
		// 	bottom: 0;
		// 	transform: translate(-50%, 50%);
		// }

		// &__sunrise {
		// 	display: block;
		// 	width: 100%;
		// 	height: 100%;
		// 	border-radius: 50%;

		// 	background: radial-gradient(
		// 		rgba(251, 217, 39, 1) 0%,
		// 		rgba(251, 217, 39, 1) 10%,
		// 		rgba(251, 217, 39, 0) 70%
		// 	);

		// 	backdrop-filter: blur(100px);
		// }

		// &__anniversary-container {
		// 	position: absolute;
		// 	left: 50%;
		// 	top: 50%;
		// 	opacity: 0;
		// 	transform: translate(-40%, -45%);

		// 	transition: all 0.8s ease-in-out;
		// 	transition-delay: 0.5s;
		// 	pointer-events: none;
		// 	z-index: 4;

		// 	&.animated {
		// 		opacity: 1;
		// 		transform: translate(-40%, -65%);
		// 	}
		// }
	}
}

@media (max-width: 1024px) {
	.header {
		// &__container {
		// 	width: 100%;
		// 	height: 100%;
		// 	background-color: var(--red-main);
		// 	display: flex;
		// 	justify-content: center;
		// 	align-items: flex-end;
		// }

		// &__logo-container {
		// 	margin-top: 63px;
		// 	z-index: 1;
		// 	position: absolute;
		// 	top: 0;
		// 	transition: all 0.5s ease-in-out;

		// 	&.animated {
		// 		left: 25%;
		// 		top: 4%;
		// 		transform: translate(-50%, -50%) scale(0.19);
		// 	}
		// }

		&__collage-container {
			width: 60%;
			height: 800px;
		}

		&__sunrise-container {
			width: 1500px;
			// height: 1500px;
			position: absolute;
			left: 50%;
			bottom: 0;
			transform: translate(-50%, 50%);
		}

		// &__sunrise {
		// 	display: block;
		// 	width: 100%;
		// 	height: 100%;
		// 	border-radius: 50%;

		// 	background: radial-gradient(
		// 		rgba(251, 217, 39, 1) 0%,
		// 		rgba(251, 217, 39, 1) 10%,
		// 		rgba(251, 217, 39, 0) 70%
		// 	);

		// 	backdrop-filter: blur(100px);
		// }

		&__anniversary-container {
			width: 65%;
			// 	position: absolute;
			// 	left: 50%;
			// 	top: 50%;
			// 	opacity: 0;
			// 	transform: translate(-40%, -45%);

			// 	transition: all 0.8s ease-in-out;
			// 	transition-delay: 0.5s;
			// 	pointer-events: none;
			// 	z-index: 4;

			&.animated {
				opacity: 1;
				transform: translate(-40%, -60%);
			}
		}
	}
}

@media (max-width: 820px) {
	.header {
		// &__container {
		// 	width: 100%;
		// 	height: 100%;
		// 	background-color: var(--red-main);
		// 	display: flex;
		// 	justify-content: center;
		// 	align-items: flex-end;
		// }

		&__logo-container {
			margin-top: 100px;
			// 	z-index: 1;
			// 	position: absolute;
			// 	top: 0;
			// 	transition: all 0.5s ease-in-out;

			// 	&.animated {
			// 		left: 25%;
			// 		top: 4%;
			// 		transform: translate(-50%, -50%) scale(0.19);
			// 	}
		}

		&__collage-container {
			width: 60%;
			height: 600px;
		}

		&__sunrise-container {
			width: 1000px;
			// 	height: 2100px;
			// 	position: absolute;
			// 	left: 50%;
			// 	bottom: 0;
			// 	transform: translate(-50%, 50%);
		}

		// &__sunrise {
		// 	display: block;
		// 	width: 100%;
		// 	height: 100%;
		// 	border-radius: 50%;

		// 	background: radial-gradient(
		// 		rgba(251, 217, 39, 1) 0%,
		// 		rgba(251, 217, 39, 1) 10%,
		// 		rgba(251, 217, 39, 0) 70%
		// 	);

		// 	backdrop-filter: blur(100px);
		// }

		&__anniversary-container {
			width: 65%;
			// 	position: absolute;
			// 	left: 50%;
			// 	top: 50%;
			// 	opacity: 0;
			// 	transform: translate(-40%, -45%);

			// 	transition: all 0.8s ease-in-out;
			// 	transition-delay: 0.5s;
			// 	pointer-events: none;
			// 	z-index: 4;

			&.animated {
				opacity: 1;
				transform: translate(-40%, -60%);
			}
		}
	}
}

@media (max-width: 480px) {
	.header {
		// &__container {
		// 	width: 100%;
		// 	height: 100%;
		// 	background-color: var(--red-main);
		// 	display: flex;
		// 	justify-content: center;
		// 	align-items: flex-end;
		// }

		// &__logo-container {
		// 	margin-top: 63px;
		// 	z-index: 1;
		// 	position: absolute;
		// 	top: 0;
		// 	transition: all 0.5s ease-in-out;

		// 	&.animated {
		// 		left: 25%;
		// 		top: 4%;
		// 		transform: translate(-50%, -50%) scale(0.19);
		// 	}
		// }

		&__collage-container {
			width: 60%;
			height: 500px;
		}

		&__sunrise-container {
			width: 600px;
			// 	height: 2100px;
			// 	position: absolute;
			// 	left: 50%;
			// 	bottom: 0;
			// 	transform: translate(-50%, 50%);
		}

		// &__sunrise {
		// 	display: block;
		// 	width: 100%;
		// 	height: 100%;
		// 	border-radius: 50%;

		// 	background: radial-gradient(
		// 		rgba(251, 217, 39, 1) 0%,
		// 		rgba(251, 217, 39, 1) 10%,
		// 		rgba(251, 217, 39, 0) 70%
		// 	);

		// 	backdrop-filter: blur(100px);
		// }

		&__anniversary-container {
			width: 65%;
			// 	position: absolute;
			// 	left: 50%;
			// 	top: 50%;
			// 	opacity: 0;
			// 	transform: translate(-40%, -45%);

			// 	transition: all 0.8s ease-in-out;
			// 	transition-delay: 0.5s;
			// 	pointer-events: none;
			// 	z-index: 4;

			&.animated {
				opacity: 1;
				transform: translate(-40%, -40%);
			}
		}
	}
}

@media (max-width: 430px) {
	.header {
		// &__container {
		// 	width: 100%;
		// 	height: 100%;
		// 	background-color: var(--red-main);
		// 	display: flex;
		// 	justify-content: center;
		// 	align-items: flex-end;
		// }

		// &__logo-container {
		// 	margin-top: 63px;
		// 	z-index: 1;
		// 	position: absolute;
		// 	top: 0;
		// 	transition: all 0.5s ease-in-out;

		// 	&.animated {
		// 		left: 25%;
		// 		top: 4%;
		// 		transform: translate(-50%, -50%) scale(0.19);
		// 	}
		// }

		&__collage-container {
			width: 60%;
			height: 500px;
		}

		&__sunrise-container {
			width: 600px;
			// 	height: 2100px;
			// 	position: absolute;
			// 	left: 50%;
			// 	bottom: 0;
			// 	transform: translate(-50%, 50%);
		}

		// &__sunrise {
		// 	display: block;
		// 	width: 100%;
		// 	height: 100%;
		// 	border-radius: 50%;

		// 	background: radial-gradient(
		// 		rgba(251, 217, 39, 1) 0%,
		// 		rgba(251, 217, 39, 1) 10%,
		// 		rgba(251, 217, 39, 0) 70%
		// 	);

		// 	backdrop-filter: blur(100px);
		// }

		&__anniversary-container {
			width: 65%;
			// 	position: absolute;
			// 	left: 50%;
			// 	top: 50%;
			// 	opacity: 0;
			// 	transform: translate(-40%, -45%);

			// 	transition: all 0.8s ease-in-out;
			// 	transition-delay: 0.5s;
			// 	pointer-events: none;
			// 	z-index: 4;

			&.animated {
				opacity: 1;
				transform: translate(-40%, -40%);
			}
		}
	}
}

@media (max-width: 390px) {
	.header {
		// &__container {
		// 	width: 100%;
		// 	height: 100%;
		// 	background-color: var(--red-main);
		// 	display: flex;
		// 	justify-content: center;
		// 	align-items: flex-end;
		// }

		&__logo-container {
			// margin-top: 40px;
			// 	z-index: 1;
			// 	position: absolute;
			// 	top: 0;
			// 	transition: all 0.5s ease-in-out;

			// 	&.animated {
			// 		left: 25%;
			// 		top: 4%;
			// 		transform: translate(-50%, -50%) scale(0.19);
			// 	}
		}

		&__collage-container {
			width: 60%;
			height: 450px;
		}

		&__sunrise-container {
			width: 600px;
			// 	height: 2100px;
			// 	position: absolute;
			// 	left: 50%;
			// 	bottom: 0;
			// 	transform: translate(-50%, 50%);
		}

		// &__sunrise {
		// 	display: block;
		// 	width: 100%;
		// 	height: 100%;
		// 	border-radius: 50%;

		// 	background: radial-gradient(
		// 		rgba(251, 217, 39, 1) 0%,
		// 		rgba(251, 217, 39, 1) 10%,
		// 		rgba(251, 217, 39, 0) 70%
		// 	);

		// 	backdrop-filter: blur(100px);
		// }

		&__anniversary-container {
			width: 65%;
			// 	position: absolute;
			// 	left: 50%;
			// 	top: 50%;
			// 	opacity: 0;
			// 	transform: translate(-40%, -45%);

			// 	transition: all 0.8s ease-in-out;
			// 	transition-delay: 0.5s;
			// 	pointer-events: none;
			// 	z-index: 4;

			&.animated {
				opacity: 1;
				transform: translate(-40%, -40%);
			}
		}
	}
}

@media (max-width: 350px) {
	.header {
		// &__container {
		// 	width: 100%;
		// 	height: 100%;
		// 	background-color: var(--red-main);
		// 	display: flex;
		// 	justify-content: center;
		// 	align-items: flex-end;
		// }

		&__logo-container {
			// margin-top: 30px;
			// 	z-index: 1;
			// 	position: absolute;
			// 	top: 0;
			// 	transition: all 0.5s ease-in-out;

			// 	&.animated {
			// 		left: 25%;
			// 		top: 4%;
			// 		transform: translate(-50%, -50%) scale(0.19);
			// 	}
		}

		&__collage-container {
			width: 60%;
			height: 350px;
		}

		&__sunrise-container {
			width: 500px;
			// 	height: 2100px;
			// 	position: absolute;
			// 	left: 50%;
			// 	bottom: 0;
			// 	transform: translate(-50%, 50%);
		}

		// &__sunrise {
		// 	display: block;
		// 	width: 100%;
		// 	height: 100%;
		// 	border-radius: 50%;

		// 	background: radial-gradient(
		// 		rgba(251, 217, 39, 1) 0%,
		// 		rgba(251, 217, 39, 1) 10%,
		// 		rgba(251, 217, 39, 0) 70%
		// 	);

		// 	backdrop-filter: blur(100px);
		// }

		&__anniversary-container {
			width: 65%;
			// 	position: absolute;
			// 	left: 50%;
			// 	top: 50%;
			// 	opacity: 0;
			// 	transform: translate(-40%, -45%);

			// 	transition: all 0.8s ease-in-out;
			// 	transition-delay: 0.5s;
			// 	pointer-events: none;
			// 	z-index: 4;

			&.animated {
				opacity: 1;
				transform: translate(-40%, -40%);
			}
		}
	}
}
</style>
