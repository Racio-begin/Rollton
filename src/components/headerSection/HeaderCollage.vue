<script setup lang="ts">
import { ref, computed } from 'vue'

// Импортируем изображения как модули
import originalImage from '@/img/collage.png'
import hoverImage from '@/img/collage-open.png'

const hover = ref(false)

const collageImage = computed(() => (hover.value ? hoverImage : originalImage))
</script>

<template>
	<div class="collage">
		<img
			:src="collageImage"
			alt="Изображение упаковки лапши быстрого приготовления"
			@mouseover="hover = true"
			@mouseleave="hover = false"
		/>
	</div>
</template>

<style lang="scss" scoped>
.collage {
	cursor: pointer;
	opacity: 1;

	& img {
		transform: scale(1);
		transition: all 0.3s ease-in-out;

		&:hover {
			transform: scale(1.05);
		}
	}

	&:hover {
		& img {
			// opacity: 0;
		}
	}
}
</style>
