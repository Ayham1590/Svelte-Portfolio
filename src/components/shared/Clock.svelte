<script>
	let timeNow = new Date(Date.now());
	const months = [
		'Jan',
		'Feb',
		'Mar',
		'Apr',
		'May',
		'Jun',
		'Jul',
		'Aug',
		'Sep',
		'Oct',
		'Nov',
		'Dec'
	];

	let day = new Date().toLocaleString('en-us', { weekday: 'long' });

	let hrs = ('0' + ((timeNow.getHours() + 24) % 12 || 12)).slice(-2);
	let min = ('0' + timeNow.getMinutes()).slice(-2);
	let sec = ('0' + timeNow.getSeconds()).slice(-2);

	setInterval(() => {
		timeNow = new Date(Date.now());

		day = new Date().toLocaleString('en-us', { weekday: 'long' });

		hrs = ('0' + ((timeNow.getHours() + 24) % 12 || 12)).slice(-2);
		min = ('0' + timeNow.getMinutes()).slice(-2);
		sec = ('0' + timeNow.getSeconds()).slice(-2);
	}, 1000);
</script>

<!-- <div class="h-full w-full rounded-md bg-gradient-to-r p-1 from-secondary to-accent"> 
<div class="flex flex-row gap-x-4 h-24 w-full items-center justify-between">
	 <div class=" h-full w-full bg-gray-800 back flex flex-row">
	<div class="flex items-center w-full justify-center text-3xl text-white font-bold">{day}</div>
	<div class="text-3xl flex items-center">:</div>
	<div class="flex items-center w-full justify-center text-3xl text-white font-bold">{hrs}</div>
	<div class="text-3xl flex items-center">:</div>
	<div class="flex items-center w-full justify-center text-3xl text-white font-bold">{min}</div>
	<div class="text-3xl flex items-center">:</div>
	<div class="flex items-center w-full justify-center text-3xl text-white font-bold">BKK</div>
</div>
</div>
</div>  -->
<div class="px-8 py-2">
	<div class="grid gap-8 items-start justify-center">
		<div class="relative group">
			<div
				class="absolute -inset-0.5 bg-gradient-to-r from-pink-600 to-purple-600 rounded-lg blur opacity-75 group-hover:opacity-100 transition duration-1000 group-hover:duration-200 animate-tilt"
			/>
			<button
				class="relative px-7 py-4 bg-black rounded-lg leading-none flex items-center divide-x divide-gray-600"
			>
				<span class="flex items-center space-x-5">
					<img class="h-6 w-6" src="../clock.png" alt="" />
					<span class="pr-6 text-gray-100 text-lg font-bold">{day}</span>
					<span class="pr-6 text-gray-100 text-lg">|</span>
					<span class="pr-6 text-gray-100 text-lg font-bold">{hrs}</span>
					<span class="pr-6 text-gray-100 text-lg font-bold">:</span>
					<span class="pr-6 text-gray-100 text-lg font-bold">{min}</span>
					<span class="pr-6 text-gray-100 text-lg">|</span>
					<span class="pr-6 text-gray-100 text-lg font-bold">BKK</span>
				</span>
				<span
					class="pl-6 text-indigo-400 group-hover:text-gray-100 transition duration-200 text-lg font-bold"
					>Welcome &darr;</span
				>
			</button>
		</div>
	</div>
</div>


