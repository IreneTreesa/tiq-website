<script>
	import { page } from '$app/stores';
import Menu from './menu.svelte';
	

	// Gallery state
	let selectedYear = $state(2024);
	let preview = null;

	const gallery = {
		2022: ["/src/media/college.png","/src/media/college.png","/src/media/college.png"],
		2023: ["/src/media/college.png","/src/media/college.png","/src/media/college.png"],
		2024: ["/src/media/college.png","/src/media/college.png","/src/media/college.png"]
	};

	function setYear(year) { selectedYear = year; }
</script>

<style>
	.no-scrollbar::-webkit-scrollbar { display: none; }
	.no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
</style>
<Menu/>


<!-- MAIN GALLERY -->
<div class="min-h-screen bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a] py-16 px-4 sm:px-6 lg:px-12">
	
	<h1 class="text-center text-4xl md:text-5xl font-[Merriweather] text-[#70B5F4] mb-12">
		Gallery
	</h1>

	<!-- YEAR SELECTOR -->
	<div class="flex justify-center gap-3 sm:gap-6 flex-wrap mb-10">
		{#each [2022, 2023, 2024] as yr}
			<button
				on:click={() => setYear(yr)}
				class={`px-5 py-2 rounded-full border border-[#70B5F4] transition
					${selectedYear === yr ? 'bg-[#70B5F4] text-black font-semibold' : 'text-[#70B5F4] hover:bg-[#143253]'}`}
			>
				{yr}
			</button>
		{/each}
	</div>

	<!-- IMAGE GRID -->
	<div class="grid grid-cols-2 md:grid-cols-3 gap-4 md:gap-6 mx-auto max-w-6xl no-scrollbar">
		{#each gallery[selectedYear] as img}
			<img
				src={img}
				alt="gallery"
				class="rounded-lg border border-[#1a2a40] cursor-pointer hover:opacity-80 transition object-cover w-full h-auto"
				on:click={() => preview = img}
			/>
		{/each}
	</div>

	<!-- IMAGE PREVIEW -->
	{#if preview}
		<div class="fixed inset-0 bg-black/80 flex justify-center items-center p-4 z-50">
			<div class="relative max-w-[90vw] max-h-[90vh]">
				<img src={preview} class="w-full h-full object-contain rounded-lg shadow-lg" />
				<button
					on:click={() => preview = null}
					class="absolute top-2 right-2 text-white text-3xl hover:scale-110"
				>✕</button>
			</div>
		</div>
	{/if}
</div>

