<script>
	import hackLogo from './assets/logo.png'
	// import heroBackground from './assets/top_bg.png'
	import backgroundVid from './assets/background.mp4'
	import './lib/Countdown.svelte'
	import ArrowDown from 'svelte-material-icons/ChevronDown.svelte';
	import Navbar from './lib/Navbar.svelte'
	
import Countdown from './lib/Countdown.svelte'
</script>

<main>
	<Navbar></Navbar>
	<video class="topBg hero" src="{backgroundVid}" autoplay muted loop></video> <!--style="background-image: url({heroBackground})"-->
		<div class="hero-content">
			<img src="{hackLogo}" alt="HackUTA Logo">
			<h1>📅 October 1-2, 2022</h1>
			<Countdown from="October 1 2022 00:00:00 UTC-0600" to="October 2 2021 23:59:59 UTC-0600"></Countdown>
			<a href="/" class="downbtn"><ArrowDown color="white" size=3rem></ArrowDown></a>
		</div>
	<div>
		<h1>Hello World</h1>
	</div>
</main>

<style lang="scss">
	.hero {
		max-width: 100%;
		height: auto;
	}
	.downbtn {
		position: relative;
		top: 4rem;
	}
	.hero-content {
		color: white;
		position: absolute;
		margin: auto;
		left: 50%;
		top: 50%;
		transform: translate(-50%, -50%);
		text-align: center;

		img {
			width: 60%;
			height: auto;
			display: block;
			margin: auto;
		}
	}
</style>
