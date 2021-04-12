<script>
	export let segment;
	let open = false;
</script>


<nav class="header">
	<div class="header-desktop">
		<a aria-current="{segment === undefined ? 'page' : undefined}" href="." class="header-desktop__navlink">hem</a>
		<a rel=prefetch aria-current="{segment === 'portfolio' ? 'page' : undefined}" href="portfolio" class="header-desktop__navlink">portfolio</a>
		<div class="header__logo"><h1 class="header__logo-title">Glim</h1><h5 class="header__logo-subtitle">Fotografi</h5></div>
		<a aria-current="{segment === 'about' ? 'page' : undefined}" href="about" class="header-desktop__navlink">om</a>
		<a aria-current="{segment === 'contact' ? 'page' : undefined}" href="contact" class="header-desktop__navlink">kontakt</a>
	</div>
	<div class="header-mobile">
		<div class="header-mobile__hamburger" on:click="{() => open = !open}">
			<div class="hamburger-line line-top" class:open="{open === true}"></div>
			<div class="hamburger-line line-middle" class:open="{open === true}"></div>
			<div class="hamburger-line line-bottom" class:open="{open === true}"></div>
		</div>
		<div class="header-mobile__drawer" class:open="{open === true}">
			<a aria-current="{segment === undefined ? 'page' : undefined}" href="." class="header-mobile__navlink" on:click="{() => open = !open}">hem</a>
			<a rel=prefetch aria-current="{segment === 'portfolio' ? 'page' : undefined}" href="portfolio" class="header-mobile__navlink" on:click="{() => open = !open}">portfolio</a>
			<a aria-current="{segment === 'about' ? 'page' : undefined}" href="about" class="header-mobile__navlink" on:click="{() => open = !open}">om</a>
			<a aria-current="{segment === 'contact' ? 'page' : undefined}" href="contact" class="header-mobile__navlink" on:click="{() => open = !open}">kontakt</a>
		</div>
	</div>
</nav>

<style>
	/* Mobile styles for header and drawer */
	.header-mobile {
		display: block;
	}
	.header-mobile__hamburger {
		position: absolute;
		top: 0;
		left: 0;
		height: 32px;
		width: 32px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		cursor: pointer;
		padding: 4px;
		z-index: 999;
	}
	.hamburger-line {
		width: 20px;
		height: 2px;
		background: black;
		transition: all 0.5s ease;
	}
	.line-top {
		margin-bottom: 5px;
	}
	.line-top.open {
		transform: rotate(45deg);
		transform-origin: top left;
		background: white;
	}
	.line-middle.open {
		opacity: 0;
		transform: translateX(-16px);
		background: white;
	}
	.line-bottom {
		margin-top: 5px;
	}
	.line-bottom.open {
		transform: translateX(-1px) rotate(-45deg);
		transform-origin: top left;
		background: white;
	}
	.header-mobile__drawer {
		position: absolute;
		top: -2000px;
		left: 0;
		width: 100vw;
		height: 0;
		display: flex;
		flex-direction: column;
		background: black;
		opacity: 0.95;
		color: white;
		transition: height 0.5s ease;
		z-index: 2;
		padding: 2em 0;
	}
	.header-mobile__drawer.open {
		height: auto;
		top: 0;
	}
	.header-mobile__navlink {
		text-align: center;
		text-decoration: none;
		color: white;
		font-family: 'Oranienbaum', serif;
		font-size: 1.5rem;
		padding: 1em 0 0.5em 0em;
		box-shadow: 0px 24px 3px -24px white;
	}

	/* Desktop styles for navbar */
	.header-desktop {
		display: none;
	}
	.header-desktop a {
		text-decoration: none;
		font-family: 'Thasadith', sans-serif;
		text-transform: uppercase;
		color: black;
		font-size: 1.2rem;
		font-weight: 700;
	}
	.header__logo {
		display: flex;
		flex-flow: column nowrap;
		align-items: center;
	}
	.header__logo-title {
		text-transform: uppercase;
		font-family: 'Oranienbaum', serif;
		font-size: 5rem;
		line-height: 3.5rem;
		letter-spacing: -0.05em;
	}
	.header__logo-subtitle {
		font-family: 'Thasadith', sans-serif;
		text-transform: uppercase;
		font-size: 1.2rem;
		letter-spacing: .1em;
		font-weight: 700;
	}


	/* Media queries for navbar */
	@media screen and (min-width: 600px){	
		.header-mobile {
			display: none;
		}
		.header-desktop {
			margin: 0 auto;
			max-width: 960px;
			display: flex;
			flex-flow: row nowrap;
			justify-content: space-around;
			align-items: center;
			padding-top: 2em;
		}
	}
	/* [aria-current] {
		position: relative;
		display: inline-block;
	}
	
	[aria-current]::after {
		position: absolute;
		content: '';
		width: calc(100% - 1em);
		height: 2px;
		display: block;
		bottom: -1px;
	} */
</style>
