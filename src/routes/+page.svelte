<script lang="ts">
	import Clock from '../components/shared/Clock.svelte';
	import AboutPage from '../components/pages/AboutPage.svelte';
	import PersonalPage from '../components/pages/PersonalPage.svelte';
	import { onMount } from 'svelte';
	import { faLongArrowRight, faRandom } from '@fortawesome/free-solid-svg-icons';
	import { page } from '$app/stores';
</script>

<div class="absolute left-0 bottom-[50px]">
	<img
		class="w-32"
		src="https://www.adeolaadeoti.xyz/_next/static/media/hand-left.c5d6f258c2bb1d7411a2276c3088bafc.webp"
		alt=""
		srcset=""
	/>
</div>

<div class="absolute right-0 top-[20px]">
	<img
		class="w-32"
		src="https://www.adeolaadeoti.xyz/_next/static/media/hand-right.162bbca06ad533d8134ecde9a4473fe4.webp"
		alt=""
		srcset=""
	/>
</div>
<div class="flex w-full justify-center h-full flex-col items-center text-center">
	<!-- <img src="../ayham.png" alt="" class="w-32 h-32" /> -->
	<h1
		data-value="< Front-End Developer />"
		class="font-extrabold text-transparent text-center item-center justify-center text-5xl bg-clip-text bg-gradient-to-r p-5 from-secondary to-accent z-10 "
	>
		{'<'} Front-End Developer {'/>'}
	</h1>

	<script>
		const letters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZ</>';

		document.querySelector('h1').onmouseover = (event) => {
			let interval;
			let iteration = 0;

			clearInterval(interval);

			interval = setInterval(() => {
				event.target.innerText = event.target.innerText
					.split('')
					.map((letter, index) => {
						if (index < iteration) {
							return event.target.dataset.value[index];
						}

						return letters[Math.floor(Math.random() * 26)];
					})
					.join('');

				if (iteration >= event.target.dataset.value.length) {
					clearInterval(interval);
				}

				iteration += 1 / 3;
			}, 30);
		};
	</script>

	<style>
		h1 {
			font-family: 'Space Mono', monospace;
			font-size: clamp(3rem, 10vw, 10rem);
		}
	</style>

	<div class="relative w-full max-w-4xl">
		<Clock />
	</div>
</div>

<section id="about" class="pb-96 scroll-m-16">
	<AboutPage />
</section>

<section id="personalprojects" class="scroll-m-16">
	<PersonalPage />
</section>

