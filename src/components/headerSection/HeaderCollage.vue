<script setup lang="ts">
import { ref } from 'vue'

// Импортируем изображения как модули
import originalImage from '@/img/collage.png'
import hoverImage from '@/img/collage-open.png'

// Состояния для отслеживания состояния клика
const imageSwitched = ref(false)

// Функция для переключения изображения при клике
const toggleImage = () => {
	imageSwitched.value = true
}
</script>

<template>
	<div class="collage">
		<img
			:src="imageSwitched ? hoverImage : originalImage"
			:class="{ clicked: imageSwitched }"
			alt="Изображение упаковки лапши быстрого приготовления"
			@click="toggleImage"
		/>
	</div>
</template>

<style lang="scss" scoped>
.collage {
	width: 100%;
	height: 100%;
	opacity: 1;

	display: flex;
	align-items: flex-end;

	& img {
		transition: all 0.3s ease-in-out;
		cursor: pointer;

		&:hover {
			animation: shake 0.25s infinite;
		}

		&.clicked {
			&:hover {
				animation: none;
			}
		}
	}
}

@keyframes shake {
	from {
		transform: translateX(0);
	}
	50% {
		transform: translateX(10px);
	}
	to {
		transform: translateX(0);
	}
}
</style>
