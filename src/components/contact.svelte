<script>
	import { page } from '$app/stores';
	function scrollToTop() {
		window.scroll({ top: 0, behavior: 'smooth' });
	}
	let tabs = $state([
		{ name: 'About Us', link: '/about' },
		{ name: 'Contact Us', link: '/contact' }
	]);
	import {Instagram, Linkedin} from 'lucide-svelte';
</script>

<div class="h-screen w-full relative flex flex-col">
	<div
		class="h-[40%] flex flex-col relative bg-gradient-to-tr from-[#020912] from-0% via-[#0b1320] via-45%
to-[#101a2a] to-100%"
	>
		<div class="flex overflow-hidden lg:flex-row md:flex-wrap sm:flex-wrap">
			<div class="flex flex-col flex-1">
				<header class="top-0 flex flex-row mt-2 font Nunito-Sans z-10 lg:pl-27 md:pl-10 sm:pl-0">
					<a href="/">
						<img class="w-20 h-21 -translate-y-3.5" src="../src/media/favicon.svg" alt="tiq" />
					</a>
					<div class="py-3.5 ml-auto text-xl">
						{#each tabs as tab}
							<a
								class="text-[#F8F3E2] px-7 font-light {$page.url.pathname === tab.link
									? 'underline underline-offset-10 font-extrabold'
									: ''}"
								href={tab.link}>{tab.name}</a
							>
						{/each}

						<a
							href="https://forms.gle/exampleGoogleFormLink"
							target="_blank"
							rel="noopener noreferrer"
							class="font-light blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-[#70B5F4] ml-7 mr-20 text-[#020913]"
							>
							Register Now
						</a>

					</div>
				</header>
			</div>
		</div>
	</div>
	<div class="bg-[#E2F0FC] h-[60%]"></div>

	<div
  class="flex flex-col absolute top-[45%] left-1/2 bg-[#A9D1F7] -translate-x-1/2 -translate-y-1/2 p-10 rounded-2xl shadow-lg"
>
  <!-- Contact title -->
  <h1 class="font-[merriweather] text-[#020913] text-center text-6xl mb-8">
    Contact Us
  </h1>

  <!-- Intro message -->
  <p class="text-base text-[#020913] mx-10 font-light leading-relaxed text-center mb-6">
    We’d love to hear from you! Whether you have a question or feedback,
    reach out to us through our social platforms.
  </p>

  <!-- Contact links (centered container, shifted slightly left) -->
  <div class="flex justify-center">
    <ul class="space-y-4 text-[#020913] transform -translate-x-10">

      <li class="flex items-center gap-3">
        <Linkedin size="22" />
        <a
          href="https://www.linkedin.com/company/illuminati-quiz-club/"
          target="_blank"
          class="underline hover:text-[#7B3C27]"
        >
          linkedin.com/company/TheIlluminatiQuizClub
        </a>
      </li>

      <li class="flex items-center gap-3">
        <Instagram size="22" />
        <a
          href="https://www.instagram.com/mec_illuminati?igsh=MW9pZHNycTNxdjhybQ=="
          target="_blank"
          class="underline hover:text-[#7B3C27]"
        >
          @mec_illuminati
        </a>
      </li>

    </ul>
  </div>

  <!-- Foundation note -->
  <p class="text-base text-[#020913] font-light leading-relaxed text-center mt-6">
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
