<script>
	import FaInstagram from 'svelte-icons/fa/FaInstagram.svelte';
	import FaBehance from 'svelte-icons/fa/FaBehance.svelte';
	import FaFacebookF from 'svelte-icons/fa/FaFacebookF.svelte';

	let currentYear = new Date().getFullYear();
</script>

<footer>
	<div class="footer-mobile">
		<div class="footer-mobile__icons">
			<div class="footer-mobile__icons-icon">
				<FaFacebookF />
			</div>
			<div class="footer-mobile__icons-icon">
				<FaBehance />
			</div>
			<a href="https://instagram.com/glimfotografi">
				<div class="footer-mobile__icons-icon">
					<FaInstagram />
				</div>
			</a>
		</div>
		<div class="footer-mobile__copyright-container">
			<span class="footer__copyright">jonssons.io © {currentYear}</span>
		</div>
	</div>
	<div class="footer-desktop">
		<div class="footer-desktop__icons">
			<a href="https://facebook.com">
				<div class="footer-desktop__icons-icon">
					<FaFacebookF />
				</div>
			</a>
			<a href="https://behance.com">
				<div class="footer-desktop__icons-icon">
					<FaBehance />
				</div>
			</a>
			<a href="https://instagram.com/glimfotografi">
				<div class="footer-desktop__icons-icon">
					<FaInstagram />
				</div>
			</a>
		</div>
		<div class="footer-desktop__copyright-container">
			<span class="footer__copyright">jonssons.io © {currentYear}</span>
		</div>
	</div>
</footer>

<style>
	footer {
		position: absolute;
		bottom: 0px;
		width: 100vw;
		height: auto;
		background: #f0f0f0;
		display: flex;
		flex-flow: row nowrap;
		align-items: center;
		justify-content: center;
	}
	.footer-mobile {
		display: flex;
		flex-flow: column nowrap;
		justify-content: center;
		align-items: center;
		margin: 0.8em 0;
	}
	.footer-mobile__icons {
		display: flex;
		flex-flow: row nowrap;
		justify-content: center;
		align-items: center;
	}
	.footer-mobile__icons-icon {
		height: 28px;
		width: 28px;
		margin: 0 0.8em;
		display: flex;
		flex-flow: row nowrap;
		align-items: center;
		color: black;
	}
	.footer-mobile__copyright-container {
		margin-top: 0.8em;
		text-align: center;
	}
	.footer__copyright {
		font-family: 'Exo', sans-serif;
		font-weight: 500;
	}
	.footer-desktop {
		display: none;
	}

	@media screen and (min-width: 600px) {
		.footer-mobile {
			display: none;
		}
		.footer-desktop {
			margin: 2em;
			width: 100vw;
			display: flex;
			flex-flow: column nowrap;
		}
		.footer-desktop__icons {
			display: flex;
			flex-flow: row nowrap;
			justify-content: flex-end;
		}
		.footer-desktop__icons-icon {
			margin: 0 1em;
			height: 36px;
			width: 36px;
			color: black;
			display: flex;
			align-items: center;
		}
		.footer-desktop__copyright-container {
			margin-top: 0.5em;
			margin-right: 1em;
			text-align: right;
		}
	}
	@media screen and (min-width: 1264px) {
		.footer-desktop {
			margin-right: 6em;
		}
	}
</style>
