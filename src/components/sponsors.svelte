<script>
  // Array of sponsors
  let sponsors = [
    { name: 'Sponsor 1', src: '/src/media/college.png', size: 'large' },
    { name: 'Sponsor 2', src: '/src/media/college.png', size: 'medium' },
    { name: 'Sponsor 3', src: '/src/media/college.png', size: 'medium' },
    { name: 'Sponsor 4', src: '/src/media/college.png', size: 'small' },
    { name: 'Sponsor 5', src: '/src/media/college.png', size: 'small' }
  ];

  // Map size to Tailwind classes
  const sizeMap = {
    large: 'w-60 h-60',
    medium: 'w-40 h-40',
    small: 'w-28 h-28'
  };
</script>

<section class="px-10 py-12 bg-[#A9D1F7] text-center">
  <h2 class="text-6xl font-[merriweather] mb-10">Our Sponsors</h2>

  <div class="flex flex-wrap justify-center items-center gap-8">
    {#each sponsors as sponsor}
      <div class="flex flex-col items-center">
        <img src={sponsor.src} alt={sponsor.name} class={`rounded-lg ${sizeMap[sponsor.size]}`} />
        <span class="mt-2 font-semibold text-[#020913]">{sponsor.name}</span>
      </div>
    {/each}
  </div>
</section>
