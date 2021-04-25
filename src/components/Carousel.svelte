<script>
	import { goto } from '@sapper/app';
	import FaAngleLeft from 'svelte-icons/fa/FaAngleLeft.svelte';
	import FaAngleRight from 'svelte-icons/fa/FaAngleRight.svelte';
	let images = [
		{
			path:
				'https://images.unsplash.com/photo-1551913902-c92207136625?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=2134&q=80',
			desc: 'An image',
		},
		{
			path:
				'https://images.unsplash.com/photo-1567165064443-ccd79f0eb3f5?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=2134&q=80',
			desc: 'An image',
		},
		{
			path:
				'https://images.unsplash.com/photo-1548435094-267366b3e3df?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=2134&q=80',
			desc: 'An image',
		},
	];
	let currentImagePath =
		'https://images.unsplash.com/photo-1551913902-c92207136625?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=2134&q=80';
	let imageCount = 1;

	function changeCount(val) {
		imageCount = imageCount + val;
		if (imageCount > images.length) {
			imageCount = 1;
		}
		if (imageCount < 1) {
			imageCount = images.length;
		}
		let index = imageCount - 1;
		currentImagePath = images[index].path;
	}
</script>

<section class="carousel__container">
	<div class="carousel__cards-mobile">
		<div class="carousel__icon-left" on:click={() => changeCount(-1)}>
			<FaAngleLeft />
		</div>
		<div
			class="carousel__image"
			style="background-image: url({currentImagePath})"
		/>
		<div class="carousel__icon-right" on:click={() => changeCount(1)}>
			<FaAngleRight />
		</div>
	</div>
	<button class="carousel__portfoliobtn" on:click={() => goto('/portfolio')}
		>Portfolio</button
	>
	<div class="carousel__cards-desktop">
		{#each images as image}
			<img src={image.path} alt={image.desc} class="carousel__slide" />
		{/each}
		<div class="carousel__icons">
			<div class="carousel__icon-left" on:click={() => changeCount(-1)}>
				<FaAngleLeft />
			</div>
			<div class="carousel__icon-right" on:click={() => changeCount(1)}>
				<FaAngleRight />
			</div>
		</div>
		<div class="carousel__indicators">
			{#each images as image}
				<div class="carousel__indicator" />
			{/each}
		</div>
	</div>
</section>

<style>
	.carousel__container {
		width: 100%;
		height: 75%;
		padding: 1.5em 0;
		display: flex;
		flex-flow: column nowrap;
		justify-content: center;
		align-items: center;
	}
	.carousel__cards-mobile {
		width: 100%;
		height: 100%;
		display: flex;
		flex-flow: row nowrap;
		align-items: center;
		justify-content: center;
	}
	.carousel__image {
		height: 100%;
		width: 50%;
		background-size: contain;
		background-position: center center;
		background-repeat: no-repeat;
		transition: ease-in 0.5s;
	}
	.carousel__icon-left,
	.carousel__icon-right {
		color: rgb(54, 54, 54);
		height: 36px;
		width: 36px;
		z-index: 10;
	}
	.carousel__portfoliobtn {
		margin: 1em 0;
		background-color: white;
		color: rgb(54, 54, 54);
		padding: 0.35em 0.8em;
		font-weight: 500;
		letter-spacing: 0.1em;
		text-transform: uppercase;
		box-shadow: none;
		border: 1px solid rgb(54, 54, 54);
	}
	.carousel__cards-desktop {
		display: none;
	}
	@media screen and (min-width: 600px) {
		.carousel__container {
			height: 85%;
			padding: 2.5em 0;
		}
	}

	@media screen and (min-width: 960px) {
		.carousel__cards-mobile {
			display: none;
		}
		.carousel__cards-desktop {
			width: 100%;
			height: 100%;
			display: flex;
		}
	}
</style>
