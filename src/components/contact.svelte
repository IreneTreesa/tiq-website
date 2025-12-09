<script>
	import { page } from '$app/stores';
	import { Instagram, Linkedin } from 'lucide-svelte';

	let tabs = [
		{ name: 'About Us', link: '/about' },
		{ name: 'Contact Us', link: '/contact' },
		{ name: 'Gallery', link: '/gallery' },
		{ name: 'Register', link: '/register' }
	];
</script>

<div class="h-screen w-full relative flex flex-col">

	<!-- DARK BLUE TOP SECTION (unchanged design) -->
	<div class="h-[40%] flex flex-col relative bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a]">
		<div class="flex overflow-hidden md:flex-wrap sm:flex-wrap">
			<div class="flex flex-col flex-1">
				<header class="top-0 flex flex-row mt-2 font-Nunito-Sans z-10 px-4 sm:px-6 md:px-10">
					<a href="/">
						<img class="w-20 h-21 -translate-y-3.5" src="../src/media/favicon.svg" alt="tiq" />
					</a>

					<!-- NAVIGATION -->
					<div class="py-3.5 ml-auto text-xl flex flex-wrap gap-2 sm:gap-4">
						{#each tabs as tab}
							<a
								href={tab.link}
								class="text-[#F8F3E2] px-4 sm:px-6 font-light
								{($page.url.pathname === tab.link) ? 'underline underline-offset-10 font-extrabold' : ''}
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

	<!-- LIGHT BLUE BOTTOM BG (unchanged) -->
	<div class="bg-[#E2F0FC] h-[60%] w-full"></div>

	<!-- CONTACT CARD -->
	<div
		class="flex flex-col items-center absolute 
		top-[45%] left-1/2 -translate-x-1/2 -translate-y-1/2
		bg-[#A9D1F7] p-8 sm:p-10 rounded-2xl shadow-lg 
		w-[90%] sm:w-3/4 md:w-2/3 lg:w-1/2"
	>

		<!-- Title -->
		<h1 class="font-[merriweather] text-[#020913] text-center text-4xl sm:text-5xl md:text-6xl mb-6">
			Contact Us
		</h1>

		<!-- Intro -->
		<p class="text-base text-[#020913] font-light leading-relaxed text-center mb-6 px-2 sm:px-6">
			We’d love to hear from you! Whether you have a question or feedback,
			reach out to us through our social platforms.
		</p>

		<!-- CONTACT LINKS -->
		<div class="flex justify-center w-full">
			<ul class="space-y-4 text-[#020913] text-center sm:text-left">

				<li class="flex flex-col sm:flex-row items-center sm:items-start gap-2 sm:gap-3">
					<div class="flex items-center gap-3">
						<Linkedin size="22" />
						<a
							href="https://www.linkedin.com/company/illuminati-quiz-club/"
							target="_blank"
							class="underline hover:text-[#7B3C27] break-all"
						>
							linkedin.com/company/TheIlluminatiQuizClub
						</a>
					</div>
				</li>

				<li class="flex flex-col sm:flex-row items-center sm:items-start gap-2 sm:gap-3">
					<div class="flex items-center gap-3">
						<Instagram size="22" />
						<a
							href="https://www.instagram.com/mec_illuminati?igsh=MW9pZHNycTNxdjhybQ=="
							target="_blank"
							class="underline hover:text-[#7B3C27] break-all"
						>
							@mec_illuminati
						</a>
					</div>
				</li>

			</ul>
		</div>

		<!-- Footer note -->
		<p class="text-base text-[#020913] font-light leading-relaxed text-center mt-6 px-4">
			In memory of <strong>Sandeep Menon</strong>, founder of TIQ and alumnus of MEC.
		</p>

		<a
			href="https://sandeepmenonfoundation.org"
			target="_blank"
			class="text-[#020913] font-medium underline hover:text-[#020913] text-center block mt-2"
		>
			Visit the Sandeep Menon Foundation →
		</a>
	</div>

</div>
