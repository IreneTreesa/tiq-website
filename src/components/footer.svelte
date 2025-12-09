<script>
	import { Instagram, Linkedin, MapPin } from "lucide-svelte";
</script>

<footer class="w-full bg-[#B3D8FF] text-[#0B1E3F] py-10 mt-0">
	<div class="max-w-6xl mx-auto px-6 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-8 sm:gap-10">

		<!-- LEFT: Title + Location -->
		<div class="flex flex-col">
			<h2 class="text-xl font-bold">The Illuminati Quiz</h2>
			<p class="mt-2 text-sm text-[#0B1E3F]/80">
				The largest intercollegiate quiz in South India.
			</p>

			<div class="mt-5 flex items-start gap-3">
				<MapPin class="w-5 h-5 flex-shrink-0" />
				<div class="text-sm">
					Govt. Model Engineering College, Thrikkakara<br />
					Kerala, India
				</div>
			</div>
		</div>

		<!-- MIDDLE: Quick Links -->
		<div class="flex flex-col mt-6 sm:mt-0">
			<h3 class="text-lg font-semibold">Quick Links</h3>
			<ul class="mt-3 space-y-2 text-sm">
				<li><a href="/" class="hover:underline">Home</a></li>
				<li><a href="/about" class="hover:underline">About Us</a></li>
				<li><a href="/gallery" class="hover:underline">Gallery</a></li>
				<li><a href="/contact" class="hover:underline">Contact</a></li>
			</ul>
		</div>

		<!-- RIGHT: Social Media -->
		<div class="flex flex-col mt-6 md:mt-0">
			<h3 class="text-lg font-semibold">Social Media</h3>
			<div class="flex items-center gap-5 mt-5">
				<a href="https://instagram.com" target="_blank" class="hover:opacity-70">
					<Instagram class="w-6 h-6" />
				</a>
				<a href="https://linkedin.com" target="_blank" class="hover:opacity-70">
					<Linkedin class="w-6 h-6" />
				</a>
			</div>
		</div>

	</div>

	<div class="text-center text-xs mt-10 opacity-70">
		© {new Date().getFullYear()} TIQ Quiz. All rights reserved.
	</div>
</footer>
