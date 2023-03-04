<script>
	import '../app.css';
	import Fa from 'svelte-fa';
	import { faGithub, faInstagram, faWhatsapp } from '@fortawesome/free-brands-svg-icons';
	import { gsap } from 'gsap';

	const navItems = [
		{
			name: 'Home',
			href: '/'
		},
		{
			name: 'About',
			href: '#about'
		},
		{
			name: 'Works',
			href: '#personalprojects'
		}
	];

	const socials = [
		{
			name: 'GitHub',
			href: 'https://github.com/Ayham1590',
			icon: faGithub
		},

		{
			name: 'Instagram',
			href: 'https://instagram.com/ayhamtamimm_?igshid=YmMyMTA2M2Y=',
			icon: faInstagram
		},

		{
			name: 'Whatsapp',
			href: 'https://wa.me/+66614914408',
			icon: faWhatsapp
		}
	];
</script>

<div
	class="bg-[#000212] w-screen h-screen text-white flex flex-col items-center relative overflow-x-hidden homescreen"
>
	<a href="/">
		<div class="fixed left-0 z-50 backdrop-blur ">
			<img class="h-14 pl-3 pt-1" src="../ayham.png" alt="" />
		</div>
	</a>
	<!-- <script src="https://code.jquery.com/jquery-2.2.4.min.js"></script>
	<style>
		.star {
			position: absolute;
			width: 2px;
			height: 2px;
			border-radius: 5px;
		}

		@keyframes twinkle {
			0% {
				transform: scale(1, 1);
				background: rgba(255, 255, 255, 0);
				animation-timing-function: linear;
			}
			40% {
				transform: scale(0.8, 0.8);
				background: rgba(255, 255, 255, 1);
				animation-timing-function: ease-out;
			}
			80% {
				background: rgba(255, 255, 255, 0);
				transform: scale(1, 1);
			}
			100% {
				background: rgba(255, 255, 255, 0);
				transform: scale(1, 1);
			}
		}
	</style>
	<script>
		for (var i = 0; i < 100; i++) {
			var star =
				'<div class="star m-0" style="animation: twinkle ' +
				(Math.random() * 5 + 5) +
				's linear ' +
				(Math.random() * 1 + 1) +
				's infinite; top: ' +
				Math.random() * $(window).height() +
				'px; left: ' +
				Math.random() * $(window).width() +
				'px;"></div>';
			$('.homescreen').append(star);
		}
	</script> -->
	<!-- <div
		class="fixed z-50 backdrop-blur w-28 h-28 ml-1 pt-0 left-0 pl-2 hover:scale-110 transition-all duration-300 ease-in-out cursor-pointer "
	>
		<a href="/">
			<img src="../ayham.png" alt="" />
		</a>
	</div> -->

	<nav
		class="fixed z-50 backdrop-blur flex w-full bg-transparent max-w-4xl border-b h-12 flex-col border-b-secondary justify-center px-4"
	>
		<div class="flex flex-row">
			<!-- This will be the navigation items, they belong on the left side -->
			<div class="flex flex-row">
				{#each navItems as navItem}
					<a
						class="first:ml-0 ml-4 flex justify-center hover:text-accent transition-all duration-200"
						href={navItem.href}
						rel="noreferrer"
					>
						{navItem.name}
					</a>
				{/each}
			</div>

			<!-- These will have to go on the right side -->
			<div class="ml-auto flex flex-row">
				{#each socials as socialItem}
					<a
						target="_blank"
						class="first:ml-0 ml-4 flex justify-center items-center hover:text-accent transition-all duration-200"
						href={socialItem.href}
						rel="noreferrer"
					>
						<Fa size="lg" icon={socialItem.icon} />
					</a>
				{/each}
			</div>
		</div>
	</nav>

	<div class="relative w-full h-full mt-12">
		<slot />
	</div>
</div>
