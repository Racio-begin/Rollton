<template>
	<div class="award">
		<img src="../../img/award.svg" alt="Награда за достижения" />
	</div>
</template>

<style lang="scss" scoped>
.award {
	width: 570px;
	aspect-ratio: 570/620; // 0.919
	display: flex;
	justify-content: center;
	align-items: center;
}

@media (max-width: 1440px) {
	.award {
		width: 520px;
		aspect-ratio: 520/566; // 0.919
	}
}
</style>
