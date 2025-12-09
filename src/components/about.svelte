<script>
	import { page } from '$app/stores';

	function scrollToTop() {
		window.scrollTo({ top: 0, behavior: 'smooth' });
	}

	let tabs = $state([
		{ name: 'About Us', link: '/about' },
		{ name: 'Contact Us', link: '/contact' },
		{ name: 'Gallery', link: '/gallery' },
		{ name: 'Register', link: '/register' }
	]);
	let scrollRef;

	function scrollLeft() {
		if (!scrollRef) return;
		scrollRef.scrollBy({ left: -scrollRef.clientWidth * 0.9, behavior: 'smooth' });
	}

	function scrollRight() {
		if (!scrollRef) return;
		scrollRef.scrollBy({ left: scrollRef.clientWidth * 0.9, behavior: 'smooth' });
	}
</script>

<!-- Dark blue bg-->
<div class="flex flex-col relative bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a]">
	<!-- Navbar -->
	<div class="flex overflow-hidden flex-wrap">
		<div class="flex flex-col flex-1">
			<header class="top-0 flex flex-row mt-2 font-Nunito-Sans z-10 px-4 sm:px-6 md:px-10 lg:pl-27">
				<a href="/">
					<img class="w-16 sm:w-20 h-auto -translate-y-1 sm:-translate-y-3.5" src="../src/media/favicon.svg" alt="tiq" />
				</a>
				<div class="py-3.5 ml-auto text-base sm:text-xl flex flex-wrap gap-2">
					{#each tabs as tab}
						<a
							href={tab.link}
							class="text-[#F8F3E2] px-3 sm:px-7 py-1 font-light 
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

	<!-- About TIQ -->
	<div class="flex flex-col lg:flex-row items-start mt-10 px-4 sm:px-10 lg:mx-20 gap-6">
		<div class="flex flex-col flex-1">
			<h1 class="text-4xl sm:text-5xl lg:text-6xl font-[merriweather] text-[#70B5F4]">About TIQ</h1>
			<p class="mt-6 text-sm sm:text-base leading-relaxed font-light text-white pr-0 sm:pr-10">
				The Illuminati Quiz (TIQ), the annual inter collegiate quiz competition organised by Govt.
				Model Engineering College is one of the largest student organised Quiz in South India. Held
				in memory of the late Sandeep Menon. Like the last edition, Illuminati Quiz will also be
				open to all categories testing the experience and mettle of working professionals against
				the young blood of quizzing.
			</p>
			<p class="mt-4 text-sm sm:text-base leading-relaxed font-light text-white pr-0 sm:pr-10">
				The new normal paved way for quizeers across the country to be part of this prestigious
				event. It also garners a large number of participants from elite colleges like IIMs and
				IITs, and numerous schools across South India and is well known not just for its attractive
				prize money but also for providing a convivial quizzing experience.
			</p>
		</div>
		<img class="w-full sm:w-64 lg:w-96 mt-6 lg:mt-0" src="/src/media/tiq_lightblue.png" alt="tiqlogo" />
	</div>
</div>

<!-- Sandeep Menon -->
<div class="flex flex-col lg:flex-row bg-[#A9D1F7] px-4 sm:px-10 py-10 lg:py-20 gap-6">
	<img class="w-40 sm:w-60 mx-auto lg:mx-0" src="/src/media/sandeep_menon.png" alt="Sandeep Menon" />
	<div class="flex flex-col lg:ml-10 text-center lg:text-left">
		<h1 class="text-3xl sm:text-4xl lg:text-6xl font-[merriweather] text-[#020913] font-normal">Sandeep Menon</h1>
		<h2 class="mt-2 sm:mt-4 text-xl sm:text-2xl lg:text-4xl italic font-[merriweather] text-[#020913]">(1984) - (2008)</h2>
		<p class="mt-4 sm:mt-6 text-sm sm:text-base lg:text-base leading-relaxed text-[#020913]">
			Sandeep Menon (batch of 2006 - Model Engineering College) is the founder and guiding spirit of
			the 'The Illuminati'. An exceptional quizzer, he is affectionately known in local quizzing
			circles as 'The Illuminatus'. He was diagnosed with cancer in 2005. Despite deteriorating
			health, Sandeep pursued his academics with utmost commitment, led the placement cell to bring
			record number of jobs on campus and instilled the spirit of quizzing in MEC. Yet, his dream
			lives on through The Illuminati and its marquee event, The Illuminati Quiz.
		</p>
	</div>
</div>

<!-- Govt Model Engineering College -->
<div class="flex flex-col relative bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a] px-4 sm:px-10 lg:px-20 py-10 lg:py-20 gap-8">
	<div class="flex flex-col lg:flex-row items-center gap-6">
		<img src="/src/media/college.png" alt="college" class="w-full sm:w-64 lg:w-100 h-auto" />
		<h1 class="text-3xl sm:text-4xl lg:text-6xl text-[#70B5F4] font-light font-[merriweather] text-center lg:text-left">
			Govt. Model <br />Engineering College
		</h1>
	</div>
	<div class="flex flex-col lg:flex-row gap-6 font-light text-white leading-relaxed">
		<p class="flex-1">
			Govt. Model Engineering College, Kochi, a premier institute of engineering education in Kerala
			is not just another engineering college producing hordes of engineering graduates every year.
			Nurturing a very diverse community of budding innovators and entrepreneurs, MEC has emblazoned
			its name as one of the most sought-after destinations for students and recruiters alike. This
			attests to MEC being ranked the 27th best engineering institute in the country.<br /><br />
			Illuminati, the quizzing fraternity of Govt. Model Engineering College, Kochi is among the
			most active students' societies of the college having conducted at least over a hundred intra
			and inter collegiate quizzes.
		</p>
		<p class="flex-1">
			Founded by the late Sandeep Menon to foster the spirit of quizzing in the student community,
			Illuminati has grown into a recognisable name all across South India. The Illuminati organizes
			the weekly Thank God Ifs Anyday (TGIX) intra college student quiz which spans a wide range of
			subjects while bringing together avid quizzers from among the students to test their mettle
			against each other in a battle of wits.
		</p>
	</div>
</div>

<!-- OUR TEAM SECTION -->
<div class="w-full bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a] py-10 sm:py-20 px-4 sm:px-10">
	<h1 class="text-center text-3xl sm:text-4xl md:text-5xl font-[merriweather] text-[#70B5F4] mb-6 sm:mb-12">
		OUR TEAM
	</h1>

	<div class="flex justify-center items-center gap-4 sm:gap-6">
		<!-- LEFT ARROW -->
		<button 
			on:click={scrollLeft}
			class="text-[#70B5F4] text-2xl sm:text-3xl cursor-pointer select-none hover:scale-110 transition"
		>
			‹
		</button>

		<!-- SCROLLABLE TEAM LIST -->
		<div 
			bind:this={scrollRef}
			class="flex gap-4 sm:gap-8 overflow-x-auto px-2 sm:px-4 scroll-smooth no-scrollbar max-w-[80vw]"
		>
			<!-- Card 1 -->
			<div class="bg-[#0d1828] flex-shrink-0 rounded-xl p-4 sm:p-6 w-40 sm:w-56 h-60 sm:h-72 flex flex-col justify-center items-center border border-[#1a2a40]">
				<div class="h-24 sm:h-32 w-24 sm:w-32 bg-[#163152] rounded-lg mb-2 sm:mb-4"></div>
				<h2 class="text-white text-lg sm:text-xl font-light">Lead</h2>
			</div>
			<div class="bg-[#0d1828] flex-shrink-0 rounded-xl p-4 sm:p-6 w-40 sm:w-56 h-60 sm:h-72 flex flex-col justify-center items-center border border-[#1a2a40]">
				<div class="h-24 sm:h-32 w-24 sm:w-32 bg-[#163152] rounded-lg mb-2 sm:mb-4"></div>
				<h2 class="text-white text-lg sm:text-xl font-light">Lead</h2>
			</div>
			<div class="bg-[#0d1828] flex-shrink-0 rounded-xl p-4 sm:p-6 w-40 sm:w-56 h-60 sm:h-72 flex flex-col justify-center items-center border border-[#1a2a40]">
				<div class="h-24 sm:h-32 w-24 sm:w-32 bg-[#163152] rounded-lg mb-2 sm:mb-4"></div>
				<h2 class="text-white text-lg sm:text-xl font-light">Lead</h2>
			</div>
			<div class="bg-[#0d1828] flex-shrink-0 rounded-xl p-4 sm:p-6 w-40 sm:w-56 h-60 sm:h-72 flex flex-col justify-center items-center border border-[#1a2a40]">
				<div class="h-24 sm:h-32 w-24 sm:w-32 bg-[#163152] rounded-lg mb-2 sm:mb-4"></div>
				<h2 class="text-white text-lg sm:text-xl font-light">Lead</h2>
			</div>
			<div class="bg-[#0d1828] flex-shrink-0 rounded-xl p-4 sm:p-6 w-40 sm:w-56 h-60 sm:h-72 flex flex-col justify-center items-center border border-[#1a2a40]">
				<div class="h-24 sm:h-32 w-24 sm:w-32 bg-[#163152] rounded-lg mb-2 sm:mb-4"></div>
				<h2 class="text-white text-lg sm:text-xl font-light">Lead</h2>
			</div>
			<div class="bg-[#0d1828] flex-shrink-0 rounded-xl p-4 sm:p-6 w-40 sm:w-56 h-60 sm:h-72 flex flex-col justify-center items-center border border-[#1a2a40]">
				<div class="h-24 sm:h-32 w-24 sm:w-32 bg-[#163152] rounded-lg mb-2 sm:mb-4"></div>
				<h2 class="text-white text-lg sm:text-xl font-light">Lead</h2>
			</div>

			<!-- Repeat cards as before -->
		</div>

		<!-- RIGHT ARROW -->
		<button 
			on:click={scrollRight}
			class="text-[#70B5F4] text-2xl sm:text-3xl cursor-pointer select-none hover:scale-110 transition"
		>
			›
		</button>
	</div>
</div>

<!-- Scroll to top button -->
<button
	on:click={scrollToTop}
	class="cursor-pointer fixed bottom-5 sm:bottom-10 right-5 sm:right-10 bg-[#70B5F4] rounded-full p-3"
>
	<svg
		xmlns="http://www.w3.org/2000/svg"
		fill="none"
		viewBox="0 0 24 24"
		stroke-width="1.5"
		stroke="currentColor"
		class="w-6 h-6 text-white"
	>
		<path
			stroke-linecap="round"
			stroke-linejoin="round"
			d="M8.25 6.75 12 3m0 0 3.75 3.75M12 3v18"
		/>
	</svg>
</button>

