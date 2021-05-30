<script>
	import Help from './Help.svelte'
	import Main from './Main.svelte'
	import Navbar from './Navbar.svelte'
	import Router from 'svelte-spa-router'

	const routes = {
		'/': Main,
		'/help': Help,
	}
</script>

<main>
	<Navbar />
	<Router {routes} />
</main>

<style>
	/* pass */
</style>