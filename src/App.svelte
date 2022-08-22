<script>
	import hackLogo from './assets/logo.png'
	import backgroundVid from './assets/background.mp4'
	import binarybackground from './assets/binarybackground.svg'
	import './lib/Countdown.svelte'
	import ArrowDown from 'svelte-material-icons/ChevronDown.svelte';
	import Navbar from './lib/Navbar.svelte'
	import Band from './lib/Band.svelte'
	import LinkBtn from './lib/LinkBtn.svelte'
	import Countdown from './lib/Countdown.svelte'
	import acmicon from './assets/acmicon.svg'

	let navLinks = [
		// {name: "Register Now", url: "/register"},

		// ADD REMAINING LATER
		// https://linguinecode.com/post/create-a-navbar-in-svelte
		{name: "Home", url:"#"},
		{name: "About", url:"#about"},
		{name: "Schedule", url:"#schedule"},
		{name: "FAQs", url: "#faq"},
		{name: "Sponsors", url: "#sponsors"}
	]
</script>

<main>
	<Navbar links={navLinks}></Navbar>
	<video style="position: absolute; width: 100%; object-fit: cover; z-index: -1;" class="topBg hero background-video" src="{backgroundVid}" autoplay muted loop></video>
	<div class="hero-content">
		<img src="{hackLogo}" alt="HackUTA Logo">
		<h1>📅 October 1-2, 2022</h1>
		<Countdown from="October 1 2022 00:00:00 UTC-0600" to="October 2 2021 23:59:59 UTC-0600"></Countdown>
		<br>
		<div>
			<LinkBtn href="https://url.lryanle.com/hackuta22">Register Now</LinkBtn>
			<LinkBtn href="https://discord.gg/zND7JCAN8y">HackUTA Discord</LinkBtn>
		</div>
		<!-- <p>Registration opens soon!</p> -->
		<a href="#downbtn" id="downbtn"><ArrowDown color="white" size="4rem"></ArrowDown></a>
		
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
	<Band id="construction" accented>
		<h1 slot="heading">Under Construction</h1>
		<div slot="content">
			<p>
				We're hard at work at putting in the final details! Feel free to register and check back <b>Monday (8/22)</b> for a complete experience! 🤠
			</p>
		</div>
	</Band>
	<Band id="footer" special>
		<h4 slot="heading">
			<a href="https://lryanle.com/acm">
				Made with <img src={acmicon} alt="acm logo" style="height: .8rem;"> by ACM at UTA 
			</a>
		</h4>
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

	#downbtn {
		position: relative;
		display: inline-block;
		top: 2rem;
	}
	
	.hero-content {
		color: white;
		padding: 10rem 1vw 5rem 1vw;
		text-align: center;
		height: 100vh;

		h1 {
			font-weight: 300;
			font-size: 3vh;
			padding: .7rem;
		}
		
		img {
			width: 70vw;
			max-width: 400px;
			height: auto;
			display: block;
			margin: auto;
			padding: .7rem 0;
		}
	}

	@media (max-width:768px){
		.background-video {
			opacity: 0%;
			overflow-x: hidden;
		}
		.hero-content {
			background: url(./assets/binarybackground.svg) no-repeat center center/cover;
		}
	}
</style>
