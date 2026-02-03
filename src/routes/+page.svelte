<script>
	import Navigation from '$lib/components/Navigation.svelte';
	import Hero from '$lib/components/Hero.svelte';
	import About from '$lib/components/About.svelte';
	import Products from '$lib/components/Products.svelte';
	import Branches from '$lib/components/Branches.svelte';
	import Contact from '$lib/components/Contact.svelte';
	import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
	<title>SunWorld Building Material LLC - Premium Building Materials UAE</title>
	<meta name="description" content="Leading distributor of premium building materials across UAE. Over 30,000 products, established since 2007. Quality materials at competitive prices." />
</svelte:head>

<Navigation />
<Hero />
<About />
<Products />
<Branches />
<Contact />
<Footer />

<style>
	:global(html) {
		scroll-behavior: smooth;
	}
</style>
