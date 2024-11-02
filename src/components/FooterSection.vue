<template>
	<footer class="footer">
		<div class="footer__container">
			<div class="footer__copyright">© 2023, Mareven. Все права защищены</div>
			<div class="footer__logo">
				Сделано в <img src="../img/logo-footer.svg" />
			</div>
		</div>
	</footer>
</template>

<style lang="scss" scoped>
.footer {
	width: 100%;

	&__container {
		height: 21px;
		padding: 0 58px 0 51px;
		margin: 19px 0;
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	&__copyright {
		font-size: 16px;
		font-weight: 400;
		color: var(--beige-optional);
	}

	&__logo {
		font-size: 16px;
		font-weight: 400;
		display: flex;
		// align-items: baseline;
		align-items: flex-start;
		// justify-content: center;
		color: var(--beige-optional);

		& img {
			margin-left: 7px;
		}
	}
}
</style>
