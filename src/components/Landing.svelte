<script>
	import Footer from "./footer.svelte";
import Sponsors from "./sponsors.svelte";

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

<div
	class="flex flex-col relative bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a]
"
>
	<div class="flex overflow-hidden lg:flex-row md:flex-wrap sm:flex-wrap">
		<div class="flex flex-col flex-1">
			<header
				class="sticky top-0 flex flex-row mt-2 font Nunito-Sans z-10 lg:pl-27 md:pl-10 sm:pl-0"
			>
				<img class="w-20 h-21 -translate-y-3.5" src="../src/media/favicon.svg" alt="tiq" />

				<div class="pr-0 py-3.5 px-10 text-xl">
					{#each tabs as tab}
						<a class="text-[#F8F3E2] px-7 font-light" href={tab.link}>{tab.name}</a>
					{/each}

					

				</div>
			</header>
			<div>
				<!--Home page Heading-->
				<h1
					class="relative text-[#70B5F4] text-center mt-15 ml-10 font-[merriweather] text-4xl md:text-6xl lg:text-8xl
 leading-tight z-10"
					>
					<span class="block">THE </span>
					<span class="block">ILLUMINATI QUIZ </span>
					<span class="block"> </span>
					<span class="block"> 2026</span>
				</h1>


				<h1
					class="relative text-[#AACCCE]
                text-2xl mt-10 ml-110 italic"
				>
					In memory of Sandeep Menon
				</h1>

				<!-- Event Info Section -->
<div class="mt-10 text-center text-white flex flex-col items-center gap-4">
    

    <p class="text-lg font-light tracking-wide">
        📅 Date: <span class="font-semibold text-[#AACCCE]"> 3 Jan 2026</span>
    </p>

    

    <a
        href="/register"
        class="mt-1 text-xl text-center blueShadow relative overflow-hidden px-7 py-3 group rounded-full bg-[#70B5F4] hover:bg-[#f2b94f] transition-all duration-300"
    >
        Register Now
    </a>
</div>



			</div>
		</div>
		<img
			class="ml-auto h-120 lg:-translate-x-30 md:-translate-x-10"
			src="../src/media/pic1.png"
			alt="speaker"
		/>
	</div>
	<div class="flex flex-row-reverse relative">
		<div class="flex flex-col relative px-10">
			<img class="w-30" src="../src/media/Frame4.png" alt="round speaker" />
			<p class="text-right mt-3 w-40 -translate-x-10 text-[#020913] italic">
				Hosted by Major Chandrakanth Nair
			</p>
		</div>
		<img class="px-15" src="../src/media/pic2.png" alt="speaker" />
	</div>
</div>
<div class="flex relative bg-[#A9D1F7]">
	<div class="flex-col my-auto ml-30 mr-30">
		<img class="w-500" src="../src/media/tiq_darkblue(2).png" alt="tiq logo" />
	</div>
	<div class="flex-col ml-auto my-65">
		<h1 class="relative text-6xl text-left font-[merriweather]">About TIQ</h1>
		<h1 class="relative text-lg text-left mt-4 mr-10">
			The Illuminati Quiz (TIQ), the annual inter collegiate quiz competition organised by Govt.
			Model Engineering College is one of the largest student organised Quiz in South India, held in
			memory of the late Sandeep Menon. Illuminati Quiz will also be open to all categories testing
			the experience and mettle of working professionals against the young blood of quizzing. The
			new normal paved way for quizeers accross the country to be part of this prestigious event.
		</h1>
		<a href='/about'>
			<h1 class="mt-4 text-sm font-extrabold text-[#020913]">Learn More &rarr;</h1>
		</a>
	</div>
</div>
<div class="flex flex-col bg-[#A9D1F7]">
	<div class="flex flex-row">
		<div class="flex flex-col ml-60">
			<h1
				class="relative text-6xl text-[#020913]
            text-left font-[merriweather] font-normal mt-50"
			>
				Get ready for <br />the Largest Quiz <br />in India
			</h1>
			<h1 class="relative text-base mt-7 font-light">
				With over 2000+ participants, which also includes participants<br /> from elite colleges
				like IIMs and IITs, here not just for our attractive <br />prize money but also for our
				convivial quizzing experience.
			</h1>
		</div>
		<img class="relative w-100 mx-auto mt-25" src="../src/media/pic3.png" alt="Frame49" />
	</div>
	<div class="flex flex-row">
		<img class="relative ml-60 w-100" src="../src/media/pic4.png" alt="Frame48" />
		<div class="flex flex-col ml-40 mt-30">
			<h1
				class="relative text-6xl text-[#020913]
            text-left font-[merriweather] font-normal"
			>
				With a Cash <br />Pool totaling <br />over ₹50,000
			</h1>
			<h1 class="relative text-base font-light mt-7">
				Cause nothing’s fun without a proper incentive. Special <br />thanks to our sponsers,
				primarily <b class="font-semibold">Ansys</b>
			</h1>
		</div>
	</div>
	<div class="flex flex-row mb-30">
		<div class="flex flex-col ml-60 mt-27">
			<h1
				class="relative text-6xl text-[#020913]
            text-left font-[merriweather] font-normal"
			>
				Hosted by Major<br /> Chandrakanth <br />Nair
			</h1>
			<h1 class="relative text-base font-light mt-7">
				One of the India’s finest Quiz Masters, Major<br /> Chandrakanth Nair is up, to give you
				that premium <br />quizzing expeirence we know him for!
			</h1>
		</div>
		<img class="relative w-100 mx-auto" src="../src/media/pic5.png" alt="Frame47" />
	</div>
</div>

<Sponsors/>

<div
	
class="flex flex-col relative bg-gradient-to-tr from-[#020912] via-[#0b1320] to-[#101a2a]
"

>
	<h1
		class="relative mt-80
    text-center text-6xl text-[#70B5F4] font-light
    font-[merriweather]"
	>
		Are you up against <br />the best of India?
	</h1>
	<h1 class="relative mt-7 text-center text-white text-base font-extralight">
		Register now to experience the most premium quizzing experience, whilst meeting <br />other
		enthusiastic quizzers, and also have a chance at winning ₹50,000
	</h1>
	

	<a
			href="/register"
			target="_blank"
			rel="noopener noreferrer"
			class="ml-auto mr-auto mt-7 text-xl text-center blueShadow relative overflow-hidden px-5 py-2 group rounded-full bg-[#70B5F4] hover:bg-[#f2b94f] transition-all duration-300"
			>
			Register Now
	</a>

	<h1 class="realtive mt-7 mb-20 text-center text-[#AACCCE] font-thin">
		** Registration fees ₹100/Team. Free for School Students
	</h1>
</div>

<button
	on:click={scrollToTop}
	class="cursor-pointer fixed bottom-10 right-10 bg-[#70B5F4] rounded-full p-3"
>
	<svg
		xmlns="http://www.w3.org/2000/svg"
		fill="none"
		viewBox="0 0 24 24"
		stroke-width="1.5"
		stroke="currentColor"
		class="size-6 fill-current text-white"
	>
		<path
			stroke-linecap="round"
			stroke-linejoin="round"
			d="M8.25 6.75 12 3m0 0 3.75 3.75M12 3v18"
		/>
	</svg>
</button>
