<script>
	import { onMount } from 'svelte';
	import Footer from "./footer.svelte";
	import Sponsors from "./sponsors.svelte";

	let showMobileMenu = false;

	function scrollToTop() {
		window.scroll({ top: 0, behavior: 'smooth' });
	}

	let tabs = [
		{ name: 'About Us', link: '/about' },
		{ name: 'Contact Us', link: '/contact' },
		{ name: 'Gallery', link: '/gallery' },
		{ name: 'Register', link: '/register' }
	];
</script>

<div class="flex flex-col relative bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a]">

	<header class="flex items-center justify-between px-4 md:px-10 py-4 bg-[#020912]">
  <!-- Logo -->
  <div class="flex items-center space-x-4">
    <img class="w-20 h-21" src="../src/media/favicon.svg" alt="tiq" />
    <span class="hidden md:flex space-x-6 text-[#F8F3E2] font-light text-lg">
      {#each tabs as tab}
        <a href={tab.link} class="hover:text-[#70B5F4]">{tab.name}</a>
      {/each}
    </span>
  </div>

  <!-- Mobile Hamburger -->
  <button class="md:hidden" on:click={() => showMobileMenu = !showMobileMenu}>
    <svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 text-[#F8F3E2]" fill="none" viewBox="0 0 24 24" stroke="currentColor">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d={showMobileMenu ? "M6 18L18 6M6 6l12 12" : "M4 6h16M4 12h16M4 18h16"} />
    </svg>
  </button>
</header>

<!-- Mobile Menu -->
{#if showMobileMenu}
  <div class="md:hidden flex flex-col bg-[#020912] text-[#F8F3E2] p-4 space-y-4">
    {#each tabs as tab}
      <a href={tab.link} class="hover:text-[#70B5F4]" on:click={() => showMobileMenu = false}>{tab.name}</a>
    {/each}
  </div>
{/if}


	<!-- Hero Section -->
<div class="flex flex-col lg:flex-row items-center justify-between px-4 md:px-10 mt-10 lg:mt-20 gap-10">
	<div class="flex flex-col flex-1 text-center lg:text-left">
		<h1 class="text-[#70B5F4] font-[merriweather] text-4xl md:text-6xl lg:text-7xl leading-tight">
			<span class="block">THE</span>
			<span class="block">ILLUMINATI QUIZ</span>
			<span class="block">2026</span>
		</h1>
		<p class="text-[#AACCCE] mt-4 italic text-lg md:text-xl">In memory of Sandeep Menon</p>
		<div class="mt-6 flex flex-col md:flex-row gap-4 justify-center lg:justify-start">
			<p class="text-white text-lg font-light">
				Date: <span class="font-semibold text-[#AACCCE]">3 Jan 2026</span>
			</p>
			<a href="/register" class="px-7 py-3 bg-[#70B5F4] rounded-full text-xl hover:bg-[#f2b94f] transition-all duration-300">
				Register Now
			</a>
		</div>
	</div>
	<img class="w-full max-w-md lg:max-w-sm" src="../src/media/pic1.png" alt="speaker" />
</div>

<!-- Hosted by Section -->
<div class="flex flex-col lg:flex-row items-center justify-center px-4 md:px-10 mt-10 gap-8">
	<div class="flex flex-col items-center lg:items-start">
		<img class="w-40 md:w-48" src="../src/media/Frame4.png" alt="round speaker" />
		<p class="mt-2 text-[#AACCCE] italic text-center lg:text-left text-sm md:text-base">
			Hosted by Major Chandrakanth Nair
		</p>
	</div>
	<img class="w-full max-w-sm lg:max-w-xs" src="../src/media/pic2.png" alt="speaker" />
</div>

<!-- Event Info Sections with Light Blue Background -->
<div class="flex flex-col gap-16 px-4 md:px-20 py-10 bg-[#A9D1F7]">
	
	<!-- Get ready for the Largest Quiz -->
	<div class="flex flex-col lg:flex-row items-center gap-10">
		<img class="w-full max-w-xs md:max-w-sm lg:max-w-sm" src="../src/media/pic3.png" alt="Frame49" />
		<div class="flex flex-col lg:w-1/2">
			<h1 class="text-4xl md:text-5xl lg:text-6xl font-[merriweather] text-[#020913]">
				Get ready for the Largest Quiz in India
			</h1>
			<p class="mt-4 text-base md:text-lg font-light text-[#020913]">
				With over 2000+ participants, including IIMs and IITs, here not just for our prize money but also for our convivial quizzing experience.
			</p>
		</div>
	</div>

	<!-- Cash Pool Section -->
	<div class="flex flex-col lg:flex-row items-center gap-10">
		<img class="w-full max-w-xs md:max-w-sm lg:max-w-sm" src="../src/media/pic4.png" alt="Frame48" />
		<div class="flex flex-col lg:w-1/2">
			<h1 class="text-4xl md:text-5xl lg:text-6xl font-[merriweather] text-[#020913]">
				With a Cash Pool totaling over ₹50,000
			</h1>
			<p class="mt-4 text-base md:text-lg font-light text-[#020913]">
				Cause nothing’s fun without proper incentive. Special thanks to our sponsors, primarily <b class="font-semibold">Ansys</b>
			</p>
		</div>
	</div>

	<!-- Hosted by Section -->
	<div class="flex flex-col lg:flex-row items-center gap-10">
		<div class="flex flex-col lg:w-1/2">
			<h1 class="text-4xl md:text-5xl lg:text-6xl font-[merriweather] text-[#020913]">
				Hosted by Major Chandrakanth Nair
			</h1>
			<p class="mt-4 text-base md:text-lg font-light text-[#020913]">
				One of India’s finest Quiz Masters, Major Chandrakanth Nair is here to give you that premium quizzing experience we know him for!
			</p>
		</div>
		<img class="w-full max-w-xs md:max-w-sm lg:max-w-sm" src="../src/media/pic5.png" alt="Frame47" />
	</div>
</div>



	<Sponsors/>

	<!-- CTA Section -->
	<div class="flex flex-col items-center bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a] text-center py-16 px-4">
		<h1 class="text-6xl text-[#70B5F4] font-[merriweather]">Are you up against the best of India?</h1>
		<p class="mt-4 text-white text-base">
			Register now to experience premium quizzing and win ₹50,000
		</p>
		<a href="/register" class="mt-6 px-5 py-2 bg-[#70B5F4] rounded-full text-xl hover:bg-[#f2b94f] transition-all duration-300">
			Register Now
		</a>
		<p class="mt-4 text-[#AACCCE] font-thin">** Registration fees ₹100/Team. Free for School Students</p>
	</div>

	<button
		on:click={scrollToTop}
		class="fixed bottom-10 right-10 bg-[#70B5F4] rounded-full p-3 cursor-pointer"
	>
		<svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-white">
			<path stroke-linecap="round" stroke-linejoin="round" d="M8.25 6.75 12 3m0 0 3.75 3.75M12 3v18" />
		</svg>
	</button>

</div>
