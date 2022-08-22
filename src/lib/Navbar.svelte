<script>
	import { fade } from "svelte/transition";
	import { Hamburger } from "svelte-hamburgers";
	let open;

	import hackLogo from "../assets/logo.png";
	export let links = [
		{ url: "/", name: "Link 1" },
		{ url: "/", name: "Link 2" },
	];
	let y = 0;
	let windowHeight;
	$: header = y > windowHeight / 2;
</script>

<svelte:window bind:scrollY={y} bind:innerHeight={windowHeight} />

{#if header}
	<header style:--opacity={Math.min(Math.max(0, y/200 - 3), 0.55)}>
	<img transition:fade={{ duration: 200 }} class="navLogo" src={hackLogo} alt="HackUTA Logo" />
	<Hamburger type="spin" --color="#ff1199" bind:open />
	{#if open}
		{#each links as link}
		<a href={link.url}>{link.name}</a>
		{/each}
	{/if}
	</header>
{/if}

<style lang="scss">
	header {
		background: rgba(0, 0, 0, var(--opacity));
		-webkit-backdrop-filter: blur(15px);
		backdrop-filter: blur(15px);
		position: fixed;
		top: 0;
		padding: 1rem;
		width: 100%;
		text-align: right;
		font-size: 100%;

		.hamburger {
			opacity: var(--opacity);
		}

		.navLogo {
			width: 40vw;
			max-width: 175px;
			float: left;
			padding: 0.5vh;
		}

		a {
			color: white;
			display: flex;
			flex-direction: column;
			justify-content: space-between;
			text-decoration: none;
			padding: 5px;
			margin: 7px;
			transition: opacity 0.3s;
			&:hover {
				opacity: 0.7;
			}
		}
		z-index: 1;
	}
	@media only screen and (min-device-width: 375px) and (max-device-width: 812px) and (-webkit-min-device-pixel-ratio: 3) {
		header {
			background: rgba(0, 0, 0, var(--opacity));
			-webkit-backdrop-filter: blur(15px);
			backdrop-filter: blur(15px);
		}
	}
</style>
