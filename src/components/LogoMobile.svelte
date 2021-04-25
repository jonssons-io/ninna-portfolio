<div class="header__logo">
    <h1 class="header__logo-title">Glim</h1>
    <h5 class="header__logo-subtitle">Fotografi</h5>
</div>


<style>
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
	@media screen and (min-width: 600px){	
		.header__logo {
			display: none;
		}
	}
</style>