<script lang="ts">
	export let cardTitle: string;
	export let cardWords: string[];
</script>

<a href="/" class=" hover:-translate-y-4 duration-150 transition-all">
	<div class="card rounded-lg">
		<div class="absolute top-0 right-0 translate-x-1/5 -translate-y-16 font-extrabold text-7xl ">
			<img
				class="h-24 w-24"
				src="1.png"
				alt=""
			/>
		</div>
		<div class="card-content">
			<h3 class="card-title">{cardTitle}</h3>
			<p class="card-subtitle">
				<!-- <span class="card-subtitle-word">But in a much more real sense, </span> -->
				{#each cardWords as cardWord}
					<span class="card-subtitle-word">{cardWord}</span>
				{/each}
			</p>
		</div>
		<div class="fa-solid fa-hat-witch card-icon">
		<img src="ayham.png" alt="" class="h-16 w-16" />
		</div>
	</div>
</a>

<style>
	:root {
		--border: rgb(3, 169, 244);
		--g1: rgb(98, 0, 234);
		--g2: rgb(236, 64, 122);
		--g3: rgb(233, 133, 18);
	}

	.card {
		aspect-ratio: 1 / 1;
		border: 0.5vmin solid var(--border);
		cursor: pointer;
		position: relative;
		width: 50vmin;
	}

	.card:hover:before {
		background-position: 100% 100%;
	}

	.card:hover > .card-content {
		background-position: -10% 0%;
	}

	.card:hover > .card-icon {
		color: white;
	}

	.card:hover > .card-content > .card-subtitle > .card-subtitle-word {
		opacity: 1;
		transform: translateY(0%);
		transition: opacity 0ms, transform 200ms cubic-bezier(0.9, 0.06, 0.15, 0.9);
	}

	.card:before {
		background: linear-gradient(
			130deg,
			transparent 0% 33%,
			var(--g1) 66%,
			var(--g2) 83.5%,
			var(--g3) 100%
		);
		background-position: 0% 0%;
		background-size: 300% 300%;
		content: '';
		height: 100%;
		left: 0px;
		pointer-events: none;
		position: absolute;
		top: 0px;
		transition: background-position 350ms ease, transform 350ms ease;
		width: 100%;
		z-index: 1;
	}

	.card-content {
		background-image: radial-gradient(rgba(255, 255, 255, 0.2) 8%, transparent 8%);
		background-position: 0% 0%;
		background-size: 5vmin 5vmin;
		height: calc(100%);
		padding: 5vmin;
		position: relative;
		transition: background-position 350ms ease;
		width: calc(100%);
		z-index: 2;
	}

	.card-title,
	.card-subtitle {
		color: white;
		font-family: 'Anek Latin', sans-serif;
		font-weight: 200;
		margin: 0px;
	}

	.card-title {
		font-size: 5vmin;
	}

	.card-subtitle {
		font-size: 3vmin;
		margin-top: 2vmin;
	}

	.card-subtitle-word {
		display: inline-block;
		margin: 0vmin 0.3vmin;
		opacity: 0;
		position: relative;
		transform: translateY(40%);
		transition: none;
	}

	.card-icon {
		bottom: 0px;
		color: rgba(255, 255, 255, 0.5);
		font-size: 7vmin;
		left: 0px;
		margin: 5vmin;
		position: absolute;
		transition: color 250ms ease;
		z-index: 2;
	}
</style>
