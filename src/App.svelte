<script>
	import Navigation from "./components/Navigation.svelte";
	import Landing from "./components/Landing.svelte";
	import About from "./components/About.svelte";
	import Skills from "./components/Skills.svelte";
	import Projects from "./components/Projects.svelte";
	import Contact from "./components/Contact.svelte";
</script>

<style>
	main {
		position: relative;
		max-width: 1000px;
		margin: 0 auto;
	}

	/* @media (min-width: 640px) {
		main {
			max-width: none;
		}
	} */
</style>

<main>
	<Navigation />
	<Landing />

	<About />
	<Contact />
	<Skills />
	<Projects />
	<footer />
</main>
