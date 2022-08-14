<script>
	import hackLogo from './assets/logo.png'
	import backgroundVid from './assets/background.mp4'
	import './lib/Countdown.svelte'
	import ArrowDown from 'svelte-material-icons/ChevronDown.svelte';
	import Navbar from './lib/Navbar.svelte'
	import Band from './lib/Band.svelte'
	import LinkBtn from './lib/LinkBtn.svelte'
	import Countdown from './lib/Countdown.svelte'
	import acmLogo from './assets/acm_logo.png'

	let navLinks = [
		{name: "Home", url:"#"},
		{name: "About", url:"#about"},
		{name: "Schedule", url:"#schedule"},
		{name: "FAQs", url: "#faq"},
		{name: "Sponsors", url: "#sponsors"}
	]
</script>

<main>
	<Navbar links={navLinks}></Navbar>
	<video class="topBg hero" src="{backgroundVid}" autoplay muted loop></video>
		<div class="hero-content">
			<img src="{hackLogo}" alt="HackUTA Logo">
			<h1>📅 October 1-2, 2022</h1>
			<Countdown from="October 1 2022 00:00:00 UTC-0600" to="October 2 2021 23:59:59 UTC-0600"></Countdown>
			<br>
			<LinkBtn href="https://discord.gg/zND7JCAN8y">Join the HackUTA Discord</LinkBtn>
			<LinkBtn href="/">Visit us on DevPost</LinkBtn>
			<!-- <p>Registration opens soon!</p> -->
			<a href="/" class="downbtn"><ArrowDown color="white" size="3.4rem"></ArrowDown></a>
			
		</div>
	<Band id="about">
		<h1 slot="heading">About HackUTA</h1>
		<div slot="content">
			<p>
				HackUTA is the annual hackathon organized by the University of Texas at Arlington chapter of the Association for Computing Machinery. For the first time in three years, HackUTA is back.
			</p>
		</div>
	</Band>
	<Band id="schedule" accented>
		<h1 slot="heading">Event Schedule</h1>
		<div slot="content">
			<p>
				Coming Soon!
			</p>
		</div>
	</Band>
	<Band id="faq">
		<h1 slot="heading">FAQs</h1>
		<div slot="content">
			<p>
				Coming Soon!
			</p>
		</div>
	</Band>
	<Band id="sponsors" accented>
		<h1 slot="heading">Sponsors</h1>
		<div slot="content">
			<p>Looking to sponsor us? Reach out to us at .</p>
		</div>
	</Band>
</main>

<style lang="scss">
	// .hero {
	// 	height: 100vh!important; // Trust me, the !important is necessary here
	// 	width: auto!important; // my bad, it wasn't - media queries >>>
	// }
	@media(min-aspect-ratio: 16/9) {
		.hero {
			width: 100%;
			height: auto;
		}
	}
	@media(max-aspect-ratio: 16/9) {
		.hero {
			height: 100%;
			width: auto;
		}
	}
	.downbtn {
		position: relative;
		display: block;
		top: 3rem;
	}
	.hero-content {
		h1 {
			font-weight: 300;
		}
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
