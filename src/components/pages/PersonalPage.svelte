<script lang="ts">
	import MagicCard from '../shared/MagicCard.svelte';
	import { onMount } from 'svelte';

	let index = 0;
	let interval = 1000;

	const rand = (min: any, max: any) => Math.floor(Math.random() * (max - min + 1)) + min;

	const animate = (star: any) => {
		star.style.setProperty('--star-left', `${rand(-10, 100)}%`);
		star.style.setProperty('--star-top', `${rand(-40, 80)}%`);

		star.style.animation = 'none';
		star.offsetHeight;
		star.style.animation = '';
	};

	onMount(() => {
		let starIntervals: NodeJS.Timer[] = [];

		for (const star of document.getElementsByClassName('magic-star')) {
			setTimeout(() => {
				animate(star);
				starIntervals.push(setInterval(() => animate(star), 1000));
			}, index++ * (interval / 3));
		}

		return () => {
			for (const interval of starIntervals) {
				clearInterval(interval);
			}
		};
	});
</script>

<h2>
	<style>
		:root {
			--purple: rgb(123, 31, 162);
			--violet: rgb(103, 58, 183);
			--pink: rgb(244, 143, 177);
		}

		@keyframes background-pan {
			from {
				background-position: 0% center;
			}

			to {
				background-position: -200% center;
			}
		}

		@keyframes scale {
			from,
			to {
				transform: scale(0);
			}

			50% {
				transform: scale(1);
			}
		}

		@keyframes rotate {
			from {
				transform: rotate(0deg);
			}

			to {
				transform: rotate(180deg);
			}
		}

		h2 {
			color: white;
			font-family: 'Rubik', sans-serif;
			font-weight: 400;
			margin: 0px;
			padding: 20px;
			text-align: center;
		}

		h2 > .magic {
			display: inline-block;
			position: relative;
		}

		h2 > .magic > .magic-star {
			--size: clamp(20px, 1.5vw, 30px);

			animation: scale 700ms ease forwards;
			display: block;
			height: var(--size);
			left: var(--star-left);
			position: absolute;
			top: var(--star-top);
			width: var(--size);
		}

		h2 > .magic > .magic-star > svg {
			animation: rotate 1000ms linear infinite;
			display: block;
			opacity: 0.7;
		}

		h2 > .magic > .magic-star > svg > path {
			fill: var(--violet);
		}

		h2 > .magic > .magic-text {
			animation: background-pan 3s linear infinite;
			background: linear-gradient(
				to right,
				var(--purple),
				var(--violet),
				var(--pink),
				var(--purple)
			);
			background-size: 200%;
			-webkit-background-clip: text;
			-webkit-text-fill-color: transparent;
			white-space: nowrap;
		}
	</style>

	<span class="magic">
		<span class="magic-star">
			<svg viewBox="0 0 512 512" />
		</span>
		<span class="magic-star">
			<svg viewBox="0 0 512 512">
				<path
					d="M512 255.1c0 11.34-7.406 20.86-18.44 23.64l-171.3 42.78l-42.78 171.1C276.7 504.6 267.2 512 255.9 512s-20.84-7.406-23.62-18.44l-42.66-171.2L18.47 279.6C7.406 276.8 0 267.3 0 255.1c0-11.34 7.406-20.83 18.44-23.61l171.2-42.78l42.78-171.1C235.2 7.406 244.7 0 256 0s20.84 7.406 23.62 18.44l42.78 171.2l171.2 42.78C504.6 235.2 512 244.6 512 255.1z"
				/>
			</svg>
		</span>
		<span class="magic-star">
			<svg viewBox="0 0 512 512">
				<path
					d="M512 255.1c0 11.34-7.406 20.86-18.44 23.64l-171.3 42.78l-42.78 171.1C276.7 504.6 267.2 512 255.9 512s-20.84-7.406-23.62-18.44l-42.66-171.2L18.47 279.6C7.406 276.8 0 267.3 0 255.1c0-11.34 7.406-20.83 18.44-23.61l171.2-42.78l42.78-171.1C235.2 7.406 244.7 0 256 0s20.84 7.406 23.62 18.44l42.78 171.2l171.2 42.78C504.6 235.2 512 244.6 512 255.1z"
				/>
			</svg>
		</span>
		<span class="magic-text text-5xl">Here are some of my works!</span>
	</span>
</h2>

<div class="grid grid-cols-3 grid-rows-1 pt-40 gap-x-28 px-20 gap-y-20">
	<MagicCard cardTitle="Calculator" cardWords={['Made using', 'Java & JavaFX']} />
	<MagicCard cardTitle="ToDo App" cardWords={['Made using', 'HTML & JavaScript']} />
	<MagicCard cardTitle="Quiz Game" cardWords={['Made using', 'HTML, CSS, JavaScript(Vue.js)']} />
</div>

<div class="bg-black">
	<div class="w-full flex flex-row flex-nowrap gap-x-4 p-4 overflow-x-hidden mt-32">
		<div class="w-64 h-24 bg-gray-400 rounded-md p-2 grid grid-cols-2 grid-rows-2">
			<div>Titles and stuff</div>
			<div>Logo</div>

			<div class="col-span-2">Text content</div>
		</div>
	</div>

	<div class="w-full flex flex-row flex-nowrap gap-x-4 p-4 overflow-x-hidden mt-4">
		<div class="w-64 h-24 bg-gray-400 rounded-md p-2 grid grid-cols-2 grid-rows-2">
			<div>Titles and stuff </div>
			<div>Logo </div>

			<div class="col-span-2">Text content555 </div>
		</div>
	</div>
</div>
