<script>
	import Nav from '../components/Nav.svelte';
	import Footer from '../components/Footer.svelte';

	export let segment;
</script>

<Nav {segment} />

<main>
	<slot />
</main>

<Footer />

<style>
	main {
		position: relative;
		max-width: 56em;
		background-color: white;
		padding: 50px 0 0 0;
		box-sizing: border-box;
		height: calc(100vh - 90px);
		margin: 0 auto;
	}
	@media screen and (min-width: 600px) {
		main {
			padding: 0;
			height: calc(100vh - 107px - 124px);
		}
	}
</style>
