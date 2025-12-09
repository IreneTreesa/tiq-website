<script>
	import { page } from '$app/stores';
	
	// Navbar tabs
	let tabs = $state([
		{ name: 'About Us', link: '/about' },
		{ name: 'Contact Us', link: '/contact' },
		{ name: 'Gallery', link: '/gallery' },
		{ name: 'Register', link: '/register' }
	]);

	// Gallery state
	let selectedYear = $state(2024);
	let preview = null;

	const gallery = {
		2022: ["/src/media/college.png","/src/media/college.png","/src/media/college.png"],
		2023: ["/src/media/college.png","/src/media/college.png","/src/media/college.png"],
		2024: ["/src/media/college.png","/src/media/college.png","/src/media/college.png"]
	};

	// Runes-mode reactive debug
	$effect(() => console.log('Selected year changed:', selectedYear));

	// Runes-mode compatible year setter
	function setYear(year) { selectedYear = year; }
</script>

<style>
	/* Hide scrollbars for gallery grid */
	.no-scrollbar::-webkit-scrollbar { display: none; }
	.no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }
</style>

<!-- NAVBAR -->
<div class="flex flex-col relative bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a]">
	<header class="flex flex-row flex-wrap items-center mt-2 font-Nunito-Sans z-10 px-4 sm:px-6 lg:px-12">
		<a href="/" class="flex-shrink-0">
			<img class="w-20 h-21 -translate-y-3.5" src="../src/media/favicon.svg" alt="tiq" />
		</a>
		<div class="ml-auto flex flex-wrap gap-2 text-xl">
			{#each tabs as tab}
				<a
					href={tab.link}
					class="text-[#F8F3E2] px-3 sm:px-5 py-1 font-light
						{$page.url.pathname === tab.link ? 'underline underline-offset-4 font-extrabold' : ''}
						hover:text-[#70B5F4] transition"
				>
					{tab.name}
				</a>
			{/each}
		</div>
	</header>
</div>

<!-- MAIN GALLERY -->
<div class="min-h-screen bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a] py-16 px-4 sm:px-6 lg:px-12">
	<h1 class="text-center text-4xl sm:text-4xl md:text-5xl font-[Merriweather] text-[#70B5F4] mb-12">
		Gallery
	</h1>

	<!-- YEAR SELECTOR -->
	<div class="flex justify-center gap-4 flex-wrap mb-10">
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
	<div class="grid grid-cols-2 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-4 md:gap-6 mx-auto max-w-6xl no-scrollbar">
		{#each gallery[selectedYear] as img}
			<div>
				<img
					src={img}
					alt="gallery"
					class="rounded-lg border border-[#1a2a40] cursor-pointer hover:opacity-80 transition w-full h-auto object-cover"
					on:click={() => preview = img}
				/>
			</div>
		{/each}
	</div>

	<!-- PREVIEW MODAL -->
	{#if preview}
		<div class="fixed inset-0 bg-black bg-opacity-80 flex justify-center items-center z-50 p-4">
			<div class="relative max-w-[90vw] max-h-[90vh]">
				<img src={preview} class="w-full h-full object-contain rounded-lg shadow-xl" />
				<button
					on:click={() => preview = null}
					class="absolute top-2 right-2 text-white text-3xl hover:scale-110"
				>
					✕
				</button>
			</div>
		</div>
	{/if}
</div>
