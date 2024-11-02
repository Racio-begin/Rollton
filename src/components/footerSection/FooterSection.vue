<script lang="ts" setup>
import links from '@/constants/links' // Импорт объектов ссылок из вашего файла
import { LinkKeys } from '@/types/LinkKeys' // Импорт enum для получения key
</script>

<template>
	<footer class="footer">
		<div class="footer__container">
			<div class="footer__copyright">
				<a :href="links[LinkKeys.Maveren]"
					>© 2023, Mareven. Все права защищены</a
				>
			</div>
			<div class="footer__logo">
				<a :href="links[LinkKeys.Intensa]"
					>Сделано в
					<img
						src="../../img/logo-footer.svg"
						target="_blank"
						alt="Логотип компании Intensa"
				/></a>
			</div>
		</div>
	</footer>
</template>

<style lang="scss" scoped>
.footer {
	width: 100%;

	&__container {
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
		color: var(--beige-optional);

		& a {
			display: flex;
			align-items: flex-start;

			& img {
				width: 63px;
				aspect-ratio: 63/15;
				margin-left: 7px;
			}
		}
	}
}

@media (max-width: 820px) {
	.footer {
		&__container {
			padding: 0 40px 0;
			margin: 15px 0;
		}
	}
}

@media (max-width: 480px) {
	.footer {
		&__container {
			padding: 0 20px 0;
			margin: 10px 0;
		}

		&__copyright {
			font-size: 12px;
		}

		&__logo {
			font-size: 12px;

			& a {
				& img {
					width: 50px;
				}
			}
		}
	}
}

@media (max-width: 375px) {
	.footer {
		&__container {
			display: flex;
			flex-direction: column;
			align-items: flex-start;
		}

		&__copyright {
			margin-bottom: 8px;
		}

		&__logo {
			& a {
				& img {
					margin-left: 5px;
				}
			}
		}
	}
}
</style>
