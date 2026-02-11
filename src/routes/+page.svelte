<script>
	import "../app.css";
	import WhatsAppButton from "$lib/components/WhatsAppButton.svelte";
	import Navigation from "$lib/components/Navigation.svelte";
	import Hero from "$lib/components/Hero.svelte";
	import About from "$lib/components/About.svelte";
	import Brands from "$lib/components/Brands.svelte";
	import Products from "$lib/components/Products.svelte";
	import Gallery from "$lib/components/Gallery.svelte";
	import Branches from "$lib/components/Branches.svelte";
	import Contact from "$lib/components/Contact.svelte";
	import Footer from "$lib/components/Footer.svelte";
</script>

<svelte:head>
	<title
		>SunWorld Building Material LLC - Premium Building Materials UAE</title
	>
	<meta
		name="description"
		content="Leading distributor of premium building materials across UAE. Over 30,000 products, established since 2007. Quality materials at competitive prices."
	/>
</svelte:head>

<Navigation />
<Hero />
<About />
<Brands />
<Products />
<Gallery />
<Branches />
<Contact />
<Footer />
<WhatsAppButton />

<style>
	:global(html) {
		scroll-behavior: smooth;
	}
</style>
