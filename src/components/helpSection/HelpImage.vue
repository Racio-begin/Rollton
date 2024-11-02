<template>
	<div class="heart-image">
		<img
			class="heart-image_1"
			src="../../img/heart-1.svg"
			alt="Сердце, внутри руки держат тепло"
		/>
		<img
			class="heart-image_2"
			src="../../img/heart-2.svg"
			alt="Сердце, внутри руки держат тепло"
		/>
	</div>
</template>

<style lang="scss" scoped>
@use '../../assets/_mixins.scss' as mixins;
@use '../../assets/_functions.scss' as functions;

.heart-image {
	width: 630px;
	aspect-ratio: 630/560; // 1.125

	margin-right: 28px;
	position: relative;
	overflow: hidden;

	&_1,
	&_2 {
		display: block;
		position: absolute;
		left: 0;
		top: 0;
		width: 100%;
		height: 100%;
		animation-duration: 4s;
		animation-timing-function: ease-in-out;
		animation-iteration-count: infinite;
	}

	&_2 {
		animation-name: fade;
	}
}

@keyframes fade {
	0% {
		opacity: 0;
	}
	50% {
		opacity: 1;
	}
	100% {
		opacity: 0;
	}
}

@media (max-width: 1920px) {
	.heart-image {
		margin-right: functions.calcVW(28);
	}
}

@media (max-width: 1440px) {
	.heart-image {
		width: 580px;
	}
}

@media (max-width: 1280px) {
	.heart-image {
		width: 480px;
		margin-right: functions.calcVW(25);
	}
}

@media (max-width: 820px) {
	.heart-image {
		width: 380px;
	}
}

@media (max-width: 768px) {
	.heart-image {
		width: 350px;
	}
}

@media (max-width: 480px) {
	.heart-image {
		margin-bottom: 30px;
	}
}

@media (max-width: 350px) {
	.heart-image {
		width: 300px;
	}
}
</style>
