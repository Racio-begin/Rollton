<script lang="ts" setup>
import image1 from '../../img/products/rollton-1.png'
</script>

<template>
	<div class="slide">
		<img
			class="slide__image"
			:src="image1"
			alt="Изображение продукции Роллтон, выпускаемое в определенны год"
		/>
		<div class="slide__circle-container">
			<svg
				class="slide__circle"
				width="282"
				height="282"
				viewBox="0 0 282 282"
				fill="none"
				xmlns="http://www.w3.org/2000/svg"
			>
				<defs>
					<clipPath id="clipCircle">
						<circle cx="141" cy="141" r="141" />
					</clipPath>
					<linearGradient
						id="paint0_linear_36_1494"
						x1="220.032"
						y1="251.8"
						x2="294.185"
						y2="333.13"
						gradientUnits="userSpaceOnUse"
					>
						<stop stop-color="white" />
						<stop
							offset="0.185014"
							stop-color="#BEBEBE"
							stop-opacity="0.886975"
						/>
						<stop offset="0.323976" stop-color="#F4A327" />
						<stop offset="0.465462" stop-color="#FFDA94" />
						<stop offset="0.600017" stop-color="#9E9E9D" stop-opacity="0" />
						<stop offset="0.932292" stop-color="#9E9E9D" stop-opacity="0" />
					</linearGradient>
				</defs>
				<g clip-path="url(#clipCircle)">
					<path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M141 0C218.872 0 282 63.208 282 141.18C282 142.869 281.96 144.549 281.9 146.223L130.945 282C57.7649 276.835 0 215.764 0 141.18C0 63.208 63.1275 0 141 0Z"
						fill="var(--red-main)"
					/>
					<g id="animatedGroup">
						<!-- <rect
							id="animatedRect"
							x="413"
							y="150"
							width="50"
							height="400"
							transform="rotate(48.0411 323.736 107.637)"
							fill="var(--light-optional)"
						/> -->

						<rect
							x="323.736"
							y="107.637"
							width="88"
							height="309.855"
							transform="rotate(48.0411 323.736 107.637)"
							fill="var(--red-main)"
						/>

						<path
							id="gradientPath"
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M321.805 219C325.235 219 328.634 219.128 332 219.369L181 355C183.651 279.44 245.671 219 321.805 219Z"
							fill="url(#paint0_linear_36_1494)"
						/>
					</g>
				</g>
			</svg>

			<img
				class="slide__shine"
				src="../../img/shine.svg"
				alt="Сияние позади слайда с продукцией Роллтон"
			/>
		</div>
		<div class="slide__plug"></div>
		<div class="slide__content">
			<h3>1999</h3>
			<p class="subtitle"><span> Первая пачка</span> вермишели</p>
		</div>
	</div>
</template>

<style lang="scss" scoped>
@use '../../assets/_functions.scss' as functions;
@use '../../assets/_mixins.scss' as mixins;

.slide {
	cursor: pointer;
	position: relative;

	&__circle-container {
		width: 366px;
		aspect-ratio: 1/1;
		margin-top: 120px;

		position: absolute;
		left: 0;
		top: -5%;
	}

	&__circle {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		z-index: 5;
	}

	&__shine {
		width: 100%;
		height: 100%;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
	}

	&__plug {
		height: 402px;
	}

	&__content {
		max-width: 340px;
		margin-left: 175px;

		display: flex;
		flex-direction: column;

		& h3 {
			font-size: 120px;
			font-weight: 700;
			color: var(--yellow);
		}

		& p {
			& span {
				width: min-content;
				white-space: nowrap;
			}
		}
	}

	&__image {
		position: absolute;
		top: 5%;
		left: 0;
		transition: all 1s ease-in-out;
		z-index: 10;
		image-rendering: optimizeQuality;

		filter: drop-shadow(10px 10px 8px rgba(0, 0, 0, 0.3));
	}

	#animatedGroup {
		transition: transform 0.8s ease-in-out;
	}

	&:hover .slide__image {
		transform: scale(1.05) rotate(8deg);
	}

	&:hover #animatedGroup {
		transform: translate(-50px, -72px);
	}
}

@media (max-width: 1920px) {
	.slide {
		&__circle-container {
			margin-top: functions.calcVH(90);
		}

		&__circle {
			width: 240px;
			aspect-ratio: 1/1;
		}

		&__plug {
			height: 360px;
		}

		&__content {
			margin-left: functions.calcVW(175);

			& h3 {
				@include mixins.adaptive-font(120, 60);
			}
		}

		&__image {
			width: 250px;
		}
	}
}

@media (max-width: 1024px) and (min-height: 1024px) {
	.slide {
		&__circle-container {
			margin-top: functions.calcVH(50);
		}
	}
}

@media (max-width: 1024px) {
	.slide {
		&__circle-container {
			width: 300px;
		}

		&__circle {
			width: 200px;
		}

		&__plug {
			height: 300px;
		}

		&__image {
			width: 200px;
		}
	}
}

@media (max-width: 820px) {
	.slide {
		&__circle-container {
			width: 250px;
		}

		&__circle {
			width: 180px;
		}

		&__plug {
			height: 250px;
		}

		&__image {
			width: 180px;
		}

		&:hover {
			&__image {
				transform: none;
			}

			#animatedGroup {
				transform: none;
			}

			& .slide__image {
				transform: none;
			}
		}
	}
}

@media (max-width: 768px) {
	.slide {
		&__circle-container {
			width: 200px;
		}

		&__circle {
			width: 150px;
		}

		&__plug {
			height: 210px;
		}

		&__image {
			width: 150px;
		}
	}
}

@media (max-width: 480px) {
	.slide {
		&__circle-container {
			width: 150px;
		}

		&__circle {
			width: 120px;
		}

		&__plug {
			height: 210px;
		}

		&__image {
			top: 10%;
			width: 120px;
		}

		&__content {
			// margin-left: 100px;

			& h3 {
				font-size: 45px;
			}
		}
	}
}

@media (max-width: 390px) {
	.slide {
		&__circle-container {
			width: 130px;
		}

		&__circle {
			width: 100px;
		}

		&__plug {
			height: 170px;
		}

		&__image {
			width: 100px;
		}

		&__content {
			& h3 {
				font-size: 38px;
			}
		}
	}
}

@media (max-width: 350px) {
	.slide {
		&__circle-container {
			width: 130px;
		}

		&__circle {
			width: 100px;
		}

		&__plug {
			height: 150px;
		}

		&__image {
			width: 95px;
		}

		&__content {
			& h3 {
				font-size: 38px;
			}
		}
	}
}
</style>
