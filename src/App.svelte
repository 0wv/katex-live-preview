<script>
	import Main from './Main.svelte'
	import Router from 'svelte-spa-router'

	const routes = {
		'/': Main,
	}
</script>

<main>
	<Router {routes} />
</main>

<style>
	/* pass */
</style>