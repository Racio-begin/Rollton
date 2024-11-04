<template>
	<div class="logo"></div>
</template>

<style lang="scss" scoped>
.logo {
	width: 1260px;
	aspect-ratio: 1260/560;
	background: url('../../img/logo-header.png');
	background-size: cover;
	background-repeat: no-repeat;
	background-position: center center;
}

@media (max-width: 1440px) {
	.logo {
		width: 1000px;
	}
}

@media (max-width: 1366px) {
	.logo {
		width: 850px;
	}
}
</style>
