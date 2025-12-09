<script>
	

	let { children } = $props();
	import Footer from '/src/components/footer.svelte';
</script>

{@render children()}
<Footer/>
