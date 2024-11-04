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

@media (max-width: 1024px) {
	.logo {
		width: 750px;
	}
}

@media (max-width: 820px) {
	.logo {
		width: 650px;
	}
}

@media (max-width: 768px) {
	.logo {
		width: 550px;
	}
}

@media (max-width: 480px) {
	.logo {
		width: 350px;
	}
}

@media (max-width: 390px) {
	.logo {
		width: 320px;
	}
}
</style>
