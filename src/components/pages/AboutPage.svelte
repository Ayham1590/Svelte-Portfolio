<script>
	import Fa from 'svelte-fa';
	import { faComputer, faDatabase, faFile, faEnvelope } from '@fortawesome/free-solid-svg-icons';

	let toggled = false;
	let color_toggled = false;
</script>

<div class="h-full flex z-10">
	<div class="flex flex-row items-center justify-center h-full w-full">
		<div class="w-full h-full ">
			<div class="flex flex-col items-center justify-center h-full ">
				<div class="w-full max-w-2xl flex">
					<div class="ml-auto">
						<h1
							class="flex flex-row text-6xl font-bold text-center first-letter:text-secondary mr-16"
						>
							<span
								class=" text-secondary inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2"
							>
								A
							</span>

							<span
								class="inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2"
								>y</span
							>
							<span
								class="inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2"
								>h</span
							>
							<span
								class="inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2"
								>a</span
							>
							<span
								class="inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2"
								>m</span
							>
						</h1>
						<h1 class="text-6xl font-bold text-center ml-16 flex flex-row">
							<span
								class="inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2"
								>T</span
							>
							<span
								class="inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2"
								>a</span
							>
							<span
								class="inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2"
								>m</span
							>
							<span
								class="inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2"
								>i</span
							>
							<span
								class="inline-block transition-all duration-75 transform cursor-default  hover:-translate-y-2 text-secondary"
								>M</span
							>
						</h1>
					</div>
				</div>
				<h2 class="text-2xl text-left w-full text-white mt-4 max-w-2xl z-0">
					<span class="flex flex-row items-center">
						<!-- svelte-ignore a11y-mouse-events-have-key-events -->
						<button
							class="transition-all duration-200"
							on:mouseenter={() => {
								toggled = true;
							}}
							on:mouseleave={() => {
								toggled = false;
							}}
							on:click={() => {
								color_toggled = !color_toggled;
							}}
						>
							<Fa
								class={`${color_toggled ? 'text-yellow-400' : ''}`}
								size="2x"
								icon={toggled ? faDatabase : faComputer}
							/>
						</button>
						<span class="ml-2 transition-all duration-200">
							{toggled ? 'Back' : 'Front'}-end Developer
						</span>
					</span>
				</h2>
				<p class="text-2xl text-white mt-4 max-w-2xl text-left">
					Lorem ipsum dolor sit, amet consectetur adipisicing elit. Voluptatum sit odit reiciendis
					quo molestiae est ut dolorum nulla magni atque nisi
				</p>
				<div class="max-w-2xl w-full mt-10 flex">
					<div class="w-full flex flex-col gap-y-4">
						<button
							class="rounded-md w-full p-2 flex flex-row items-center max-w-xs ml-auto h-16 transition-all duration-75 transform cursor-default hover:text-secondary hover:-translate-y-2 text-white"
						>
							<div class="flex flex-row justify-center items-center align-items-center">
								<span class="mr-2">
									<Fa size="3x" icon={faEnvelope} />
								</span>
								<a href="mailto:ayham.tamim2@gmail.com">
									<span class="font-bold text-4xl">Email</span>
								</a>
							</div>
						</button>

						<button
							class="rounded-md w-full p-2 flex flex-row items-center max-w-xs ml-auto h-16 transition-all duration-75 transform cursor-default hover:text-secondary hover:-translate-y-2 text-white"
						>
							<div class="ml-auto flex flex-row justify-center items-center allign-items-center">
								<a href="../Resume.pdf" target="_blank">
									<span class="font-bold text-4xl">Resume</span>
								</a>
								<span class="ml-2">
									<Fa size="3x" icon={faFile} />
								</span>
							</div>
							<div>
								<span> Vote for me !</span>
							<a>
								
							</a>
								</div>
						</button>
					</div>
				</div>
			</div>
		</div>

		<div class="w-full h-full flex justify-center items-center">
			<img src="../bg1.png" alt="" />
		</div>
	</div>
</div>
