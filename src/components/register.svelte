<script>
	import { page } from '$app/stores';

	function scrollToTop() {
		window.scroll({ top: 0, behavior: 'smooth' });
	}

	let tabs = $state([
		{ name: 'About Us', link: '/about' },
		{ name: 'Contact Us', link: '/contact' },
		{ name: 'Gallery', link: '/gallery' },
		{ name: 'Register', link: '/register' }
	]);
</script>

<!-- NAVBAR -->
<div class="flex flex-col relative bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a]">
	<div class="flex overflow-hidden lg:flex-row md:flex-wrap sm:flex-wrap">
		<div class="flex flex-col flex-1">
			<header class="top-0 flex flex-row mt-2 font-Nunito-Sans z-10 lg:pl-27 md:pl-10 sm:pl-0">
				<a href="/">
					<img class="w-20 h-21 -translate-y-3.5" src="../src/media/favicon.svg" alt="tiq" />
				</a>
				<div class="py-3.5 ml-auto text-xl flex flex-wrap gap-2">
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
	</div>
</div>

<!-- REGISTER SECTION -->
<div class="flex flex-col lg:flex-row items-center lg:items-start justify-center gap-10 px-6 md:px-12 py-20 bg-[#0b1320] min-h-screen">

  <!-- LEFT BOX -->
  <div class="bg-[#A9D1F7] p-8 rounded-2xl flex-1 max-w-lg shadow-lg w-full">
    <h2 class="text-3xl text-[#0b1320] font-bold mb-4">General Rules</h2>

    <p class="text-[#0b1320]/90 text-lg mb-6 leading-relaxed">
      1. <br/>
      2. <br/>
      3. <br/>
      4. <br/>
      5. The organizers reserve the right to make final decisions.
    </p>

    <a href="/rules.pdf" download
       class="px-6 py-3 rounded-full bg-[#0b1320] text-[#A9D1F7] font-bold hover:bg-[#143253] transition-all duration-300">
      Download Rules PDF
    </a>
  </div>

  <!-- RIGHT -->
  <div class="flex flex-col justify-center flex-1 max-w-md text-[#AACCCE] w-full h-full lg:h-auto">

    <div class="space-y-3 mt-10 lg:mt-0">
      <p class="text-lg"><span class="font-semibold">Date:</span> 3 Jan 2026</p>
      <p class="text-lg"><span class="font-semibold">Time:</span> 10:00 AM - 3:00 PM</p>
      <p class="text-lg"><span class="font-semibold">Venue:</span> ABC</p>
    </div>

    <a href="https://forms.gle/exampleGoogleFormLink" target="_blank"
       class="self-start mt-6 px-6 py-3 rounded-full bg-[#70B5F4] text-white font-bold hover:bg-[#f2b94f] transition-all duration-300">
      Register Now
    </a>

  </div>

</div>
