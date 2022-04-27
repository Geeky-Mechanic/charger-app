<script>
	/* --->  Components  <--- */
	import Navbar from './components/Navbar.svelte';
	import Footer from './components/Footer.svelte';
	/* --->  Pages  <--- */
	import Contact from './pages/Contact.svelte';
	import About from './pages/About.svelte';
	import Services from './pages/Services.svelte';


	let activePage = 'About';

	let items = ['About', 'Contact', 'Services'];

	const handleChange = (e) => {
		activePage = e.detail;
	};


</script>

<main>

	<Navbar on:pageChange={handleChange} {activePage} {items} />
	{#if activePage === 'About'}
	<About />
	{:else if activePage === 'Contact'}
	<Contact />
	{:else if activePage === 'Services'}
	<Services />
	{/if}
	<Footer on:pageChange={handleChange} {activePage} {items} />

</main>

<style>

</style>