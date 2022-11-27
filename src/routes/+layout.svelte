<script>
	import '../app.css';
	import Navbar from './lib/Navbar.svelte';
	import Footer from './lib/Footer.svelte';
</script>

<div class="min-h-screen w-full bg-indigo-900 flex flex-col justify-between">
	<div class="h-full">
		<Navbar />
		<div class="flex flex-col px-4 md:px-10 lg:px-40 py-4 text-white text-lg">
			<slot />
		</div>
	</div>
	<Footer />
</div>
