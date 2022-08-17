<script>
	import hackLogo from './assets/logo.png'
	import backgroundVid from './assets/background.mp4'
	import './lib/Countdown.svelte'
	// import ArrowDown from 'svelte-material-icons/ChevronDown.svelte';
	// import Navbar from './lib/Navbar.svelte'
	// import Band from './lib/Band.svelte'
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
	<!-- <Navbar links={navLinks}></Navbar> -->
	<div class="no-overflow">
		<video class="topBg hero" src="{backgroundVid}" autoplay muted loop></video>
	</div>
	<div class="hero-content">
		<img class="logo" src="{hackLogo}" alt="HackUTA Logo">
		<h1>📅 October 1-2, 2022</h1>
		<Countdown from="October 1 2022 00:00:00 UTC-0600" to="October 2 2021 23:59:59 UTC-0600"></Countdown>
		<br>
		<div>
			<LinkBtn href="https://discord.gg/zND7JCAN8y">HackUTA Discord</LinkBtn>
			<!-- <LinkBtn href="/">Visit us on DevPost</LinkBtn> -->
		</div>
		<!-- <p>Registration opens soon!</p> -->
		<!-- <a href="#downbtn" id="downbtn"><ArrowDown color="white" size="4rem"></ArrowDown></a> -->
		
	</div>
	<!-- <Band id="about">
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
	</Band> -->
</main>

<style lang="scss">
	// .hero {
	// 	height: 100vh!important; // Trust me, the !important is necessary here
	// 	width: auto!important; // my bad, it wasn't - media queries >>>
	// }
	@media only screen and (max-width: 390px) {
		.topBg {
			filter: blur(2px);
		}

		//smaller date text
		h1 {
			font-size: 1.5rem;
		}

		//bigger logo text
		.logo {
			width: 80vw !important;
		}

	}

	@media(min-aspect-ratio: 16/9) {
		.hero {
			width: 100vh;
			height: auto;
		}
	}
	@media(max-aspect-ratio: 16/9) {
		.hero {
			height: 100vh;
			width: auto;
		}
	}

	.no-overflow {
		overflow: hidden;
	}

	#downbtn {
		position: relative;
		display: inline-block;
		top: 2rem;
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
		width: 80%;

		img {
			width: 40vw;
			height: auto;
			display: block;
			margin: auto;
		}
	}
</style>
