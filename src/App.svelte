<script>
  import hackLogo from "./assets/logo.png";
  import backgroundVid from "./assets/background.mp4";
  import binarybackground from "./assets/binarybackground.svg";
  import "./lib/Countdown.svelte";
  import ArrowDown from "svelte-material-icons/ChevronDown.svelte";
  import Navbar from "./lib/Navbar.svelte";
  import Band from "./lib/Band.svelte";
  import LinkBtn from "./lib/LinkBtn.svelte";
  import Countdown from "./lib/Countdown.svelte";
  import acmicon from "./assets/acmicon.svg";
  import statefarm from "./assets/sponsors/statefarm.png";
  import utacse from "./assets/sponsors/utacse.png";
  import mlh from "./assets/sponsors/mlh.png";
  import rc from "./assets/sponsors/raisingcanes.png";
  import standout from "./assets/sponsors/standout.jpg";
  import cockroachlabs from "./assets/sponsors/cockroachlabs.png";
  import deso from "./assets/sponsors/deso.png";
  import domaincom from "./assets/sponsors/domaincom.png";
  import twilio from "./assets/sponsors/twilio.png";
  import wix from "./assets/sponsors/wix.png";
  import gdscuta from "./assets/sponsors/gdscuta.png";
  import techtreeroot from "./assets/sponsors/techtreeroot.png";
  import DesktopNavbar from "./lib/DesktopNavbar.svelte";
  import Calendar from "@event-calendar/core";
  import List from "@event-calendar/list";
  import TimeGrid from "@event-calendar/time-grid";
  import { events } from "./lib/events_list.js";
  import Interaction from "@event-calendar/interaction";

  // Calendar
  let plugins = [List, TimeGrid, Interaction];
  let options = {
    view: "timeGridDay",
    //date: '2022-10-1',
    views: {
      timeGridDay: { pointer: true, date: "2022-10-01" },
      timeGridWeek: { pointer: true },
    },
    firstDay: 1, // start week on Monday
    height: "60vh",
    editable: false,
    eventStartEditable: false,
    eventDurationEditable: false,
    headerToolbar: {
      start: "prev,next today",
      center: "title",
      end: "timeGridWeek,timeGridDay,listMonth",
    },
    nowIndicator: true,
    scrollTime: "09:30:00",
    slotDuration: "00:15:00",
    flexibleSlotTimeLimits: false,
    highlightedDates: ["2022-10-01", "2022-10-02"],
    events: events,
  };

  // Navbar links
  let navLinks = [
    // {name: "Register Now", url: "/register"},

    // ADD REMAINING LATER
    // https://linguinecode.com/post/create-a-navbar-in-svelte
    {
      name: "Home",
      url: "#",
    },
    {
      name: "About",
      url: "#about",
    },
    {
      name: "Schedule",
      url: "#schedule",
    },
    {
      name: "FAQs",
      url: "#faq",
    },
    {
      name: "Sponsors",
      url: "#sponsors",
    },
  ];

  window.onload = function test() {
    if (window.innerWidth < 767) {
      document.getElementsByClassName("ec-button-group")[1].style.display = "none";
      document.getElementsByClassName("ec-button-group")[0].style["margin-right"] = "0";
      document.getElementsByClassName("calendar-container-container")[0].style["padding"] = '.5rem 0rem .25rem 0rem';
      document.getElementsByClassName("calendar-container")[0].style["margin-left"] = '2vw';
      document.getElementsByClassName("calendar-container")[0].style["margin-right"] = '2vw';
      document.getElementsByClassName("calendar-container")[0].style["padding"] = '1.2rem';
      document.getElementsByClassName("ec-title")[0].style["padding"] = '1.5rem';
      document.getElementsByClassName("ec-toolbar")[0].style["flex-wrap"] = "wrap";
    }
  }
</script>

<main>
  <Navbar links={navLinks} />
  <DesktopNavbar links={navLinks} />
  <video
    style="position: absolute; width: 100%; object-fit: cover; z-index: -1;"
    class="topBg hero background-video"
    src={backgroundVid}
    autoplay
    muted
    loop
  />
  <div class="hero-content">
    <img src={hackLogo} alt="HackUTA Logo" />
    <h1 style="margin-top:5vh; margin-bottom: 2.5vh; font-size: 2rem">📅 October 1-2, 2022</h1>
    <!-- <Countdown
      from="October 1 2022 00:00:00 UTC-0600"
      to="October 2 2021 23:59:59 UTC-0600"
    /> -->
    <br />

    <!-- <h2>Registration is now closed.<br>Walk-in registration updates are on our discord.<br>Thank you to everyone who applied this year!<br><br></h2> -->
    <div>
      <!-- <LinkBtn href="https://url.lryanle.com/hackuta22">Register Now</LinkBtn> -->
      <LinkBtn href="https://discord.gg/zND7JCAN8y">HackUTA Discord</LinkBtn>
    </div>
    <!-- <p>Registration opens soon!</p> -->
    <a href="#about" id="downbtn"> <ArrowDown color="white" size="4rem" /></a>
  </div>
  <Band id="about">
    <h1 slot="heading">About HackUTA</h1>
    <div slot="content" class="about">
      <p>
        HackUTA 2022 will be returning this fall as an immersive hackathon for
        college students, both beginners and hackathon natives
        from <b style="color: var(--primary-color);">October 1-2, 2022</b>. As
        spots are limited this year, priority will be given on a first-come
        basis. Students from underrepresented groups are highly encouraged to
        attend. Information and updates can be found on our
        <a
          href="https://instagram.com/acmuta"
          target="_blank"
          style="color: var(--primary-color);"><u>Instagram</u></a
        >.
      </p>
      <br /><br />

      <h2>What is HackUTA?</h2>
      <p>
        HackUTA, one of North Texas' largest hackathons, is a 24-hour marathon
        for students to design, develop, and pitch a project from scratch. <b
          style="color: var(--primary-color);"
          >Regardless of experience, skill, major, or background</b
        >, students will work together to pitch the best solution possible.
      </p>
      <br /><br />

      <h2>Why join HackUTA 2022?</h2>
      <p>
        The University of Texas at Arlington takes pride as one of the nation’s
        most diverse undergraduate student bodies (National #3, Texas #1),
        according to <i>U.S. News & World Report’s 2022 Best Colleges</i>
        rankings. Take on challenges against and alongside one-of-a-kind teams! Develop
        skills and make friends at our workshops, socials, mini-event games, and
        challenges. We will be providing
        <b style="color: var(--primary-color);"
          >free meals, snacks, boba, and swag bags to all registered attendees</b
        >. Aditionally, a
        <b style="color: var(--primary-color);">free HackUTA 2022 T-shirt</b> will
        be awarded to students who demo their project for potential prizes.
      </p>
      <br /><br />

      <h2>
        How do I prepare? What if I'm a beginner? What will be available for me?
      </h2>
      <p>
        We will be hosting three workshops before the event: <b>(1) Intro. to Python & Hackathons</b> <a href="https://www.youtube.com/watch?v=UlFFZiaUVK8" target="_blank" style="color: var(--primary-color);">[Recording]</a> <a href="https://drive.google.com/file/d/16ZiwuHwTO09uqixnvA1NrI0gOXzyJiz-/view?usp=sharing" target="_blank" style="color: var(--primary-color);">[Intro. to Python Slides]</a> <a href="https://drive.google.com/file/d/1DNJHDCewPFe1iilo5AwauVpC8F6viC0l/view?usp=sharing" target="_blank" style="color: var(--primary-color);">[Intro. to Hack Slides]</a>, <b>(2) Intro. to Webdesign with Mobi</b>, and <b>(3) Intro to C# with Paycom</b>.
        During the event, there will be technical—and
        non-technical—opportunities hosted throughout, and mentors ready to
        assist throughout the 24-hour marathon.
      </p>
      <br>
    </div>
  </Band>
  <Band id="schedule" accented>
    <h1 slot="heading">Event Schedule</h1>
  </Band>
  <div
    style="padding: 1rem 2rem; background: #ff1199;"
    class="calendar-container-container"
  >
    <div
      style="margin-left: 10vw; margin-right: 10vw; color: black; background: white; padding: 3rem; border-radius: 20px"
      class="calendar-container"
    >
      <Calendar {plugins} {options} />
    </div>
  </div>
  <Band id="faq">
    <h1 slot="heading">FAQs</h1>
    <div slot="content">
      <br />
      <div class="row">
        <div class="col">
          <div class="tabs col1">
            <div class="tab">
              <input type="checkbox" id="chck1" />
              <label class="tab-label" for="chck1">What is a hackathon?</label>
              <div class="tab-content">
                A hackathon is a event <b>24-hour competition</b> where
                students, in teams of up to 4, build and pitch an idea against
                other groups for <b>prizes</b>. In the end, it's all about
                learning new skills and coming up with creative solutions using
                technology. To help you along the way, we provide
                <b>mentorship and workshops</b>. Beginners are welcome!
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck2" />
              <label class="tab-label" for="chck2">How do teams work?</label>
              <div class="tab-content">
                <b>Teams can be up to 4 members</b>. If you don't have a team,
                don’t worry! Joining a team of new friends is the best part of a
                hackathon. We will have <b>team matching available</b> for everyone
                on the day of the event, but if you would like to ask around in our
                discord and create a team beforehand, that's okay too! Team member
                assignment will be confirmed when adding members and submitting your
                project through Devpost at the end of the hacking period.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck3" />
              <label class="tab-label" for="chck3"
                >How much does attending cost?</label
              >
              <div class="tab-content">
                HackUTA 2022 will be <b>completely free</b> to hackers! We will
                be providing meals, snacks, boba, and swag for <b>$FREE.99</b>.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck4" />
              <label class="tab-label" for="chck4"
                >Will there be travel reimbursements?</label
              >
              <div class="tab-content">
                As of right now, there is <b
                  >no plan to provide travel reimbursements</b
                >. However, if room in our budget appears, we will make a
                notification during the event.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck5" />
              <label class="tab-label" for="chck5"
                >Where and when is HackUTA 2022?</label
              >
              <div class="tab-content">
                HackUTA will be hosted in <b>Nedderman Hall</b>, located on
                UTA's company. The event will take place
                <b>October 1-2, 2022</b>! Exact schedule coming soon.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck6" />
              <label class="tab-label" for="chck6"
                >Will hardware be provided?</label
              >
              <div class="tab-content">
                Unfortunately, <b>we cannot provide hardware</b> this year but if
                you have your own, you’re more than welcome to submit hardware projects!
              </div>
            </div>
          </div>
        </div>
        <div class="col">
          <div class="tabs col2">
            <div class="tab">
              <input type="checkbox" id="chck7" />
              <label class="tab-label" for="chck7">Are there any rules?</label>
              <div class="tab-content">
                <b
                  >All work must be done during the 24-hour period of the event</b
                >. You can't demo something you didn't build. Don't talk about
                Fight Club. All attendees (hackers, supporters, mentors,
                volunteers, etc.) must abide by the
                <a
                  href="https://static.mlh.io/docs/mlh-code-of-conduct.pdf"
                  style="color: var(--primary-color)"
                  ><u>MLH Code of Conduct</u></a
                >.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck8" />
              <label class="tab-label" for="chck8"
                >Can I participate with no experience?</label
              >
              <div class="tab-content">
                We encourage everyone to come, regardless of skill level. There
                is <b>no experience required</b> and there are many
                opportunities to learn and grow. We will host <b>workshops</b>
                and have <b>mentors</b> available to help you along the way.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck9" />
              <label class="tab-label" for="chck9"
                >What do I need to bring?</label
              >
              <div class="tab-content">
                Bring your <b>yourself</b>, your <b>valid university ID</b>, a
                form of <b>ID</b> proving you are over 18 years old,
                <b>laptop</b>, <b>charger</b> for your computer, and
                <b>any other accessory</b> you might need within 24 hours. We will
                provide internet service; however, we recommend installing any necessary
                software, compilers, packages, tools, and other related items before
                the event. Firearms, weapons, alcohol, illegal drugs, and power tools
                are not allowed. Smiles and high-fives are welcome. 🤠🤚
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck10" />
              <label class="tab-label" for="chck10"
                >What do I need to wear?</label
              >
              <div class="tab-content">
                Wear whatever you are <b>most comfortable</b> in! No need to wear
                anything professional. However, we do require you to be within the
                MLH Code of Conduct.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck11" />
              <label class="tab-label" for="chck11"
                >How do I volunteer at HackUTA?</label
              >
              <div class="tab-content">
                Volunteer applications will go live <b
                  >within the first two weeks after registration opens</b
                >. Be sure to check your emails to get a reminder before
                volunteer applications open.
              </div>
            </div>
            <div class="tab">
              <input type="checkbox" id="chck12" />
              <label class="tab-label" for="chck12"
                >When will registration end and is there a limit?</label
              >
              <div class="tab-content">
                <b
                  >Priority Registration opens August 22nd and closes on
                  September 14th at 11:59 PM CDT</b
                >. If you are accepted, you will have a week to confirm your
                registration. If you are not accepted at this time, your
                application will be reviewed again when
                <b
                  >registration closes completely on September 28th, 11:59pm CDT</b
                >.
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </Band>
  <Band id="sponsors" accented>
    <h1 slot="heading">Sponsors</h1>
    <div slot="content">
      <br />
      <ul
        style="display: flex; justify-content: space-evenly; align-items: center; flex-flow: row wrap; gap: 10px 30px"
      >
        <li>
          <img
            src={statefarm}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="StateFarm"
          />
        </li>
        <li>
          <img
            src={utacse}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="UTA Department of Computer Science"
          />
        </li>
        <li>
          <img
            src={mlh}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="Major League Hacking"
          />
        </li>
        <li>
          <img
            src={techtreeroot}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="Tech Tree Root"
          />
        </li>
        <li>
          <img
            src={standout}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="Standout Stickers"
          />
        </li>
        <li>
          <img
            src={cockroachlabs}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="Cockroach Labs"
          />
        </li>
        <li>
          <img
            src={deso}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="DeSo"
          />
        </li>
        <li>
          <img
            src={domaincom}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="Domain.com"
          />
        </li>
        <li>
          <img
            src={twilio}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="Twilio"
          />
        </li>
        <li>
          <img
            src={wix}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="Wix"
          />
        </li>
        <li>
          <img
            src={gdscuta}
            style="border-radius: 20px; max-width: 256px; width: 70vw"
            alt="Google Developer Student Club at UT Arlington"
          />
        </li>
      </ul>
      <br />
      <!-- <p>
        Want to sponsor us? <br />Reach out at <u>sponsor[at]hackuta[dot]org</u>
      </p> -->
    </div>
  </Band>
  <!-- <Band id="construction" accented>
		<h1 slot="heading">Under Construction</h1>
		<div slot="content">
			<p>
				We're hard at work at putting in the final details! Feel free to register and check back <b>Monday (8/22)</b> for a complete experience! 🤠
			</p>
		</div>
	</Band> -->
  <Band id="footer" special>
    <h4 slot="heading">
      <a
        href="https://lryanle.com/acm"
        style="color: white; text-decoration: none"
      >
        Made with <img
          src={acmicon}
          alt="acm logo"
          style="height: .8rem; width: 1rem;"
        /> by ACM at UTA
      </a>
    </h4>
  </Band>
</main>

<style lang="scss">
  // .hero {
  // 	height: 100vh!important; // Trust me, the !important is necessary here
  // 	width: auto!important; // my bad, it wasn't - media queries >>>
  // }
  @media (min-aspect-ratio: 16/9) {
    .hero {
      width: 100%;
      height: auto;
    }
  }

  @media (max-aspect-ratio: 16/9) {
    .hero {
      height: 100%;
      width: auto;
    }
  }

  #downbtn {
    position: relative;
    display: inline-block;
    top: 1.5rem;
    padding: 0 0 0 0.2rem;
  }

  .hero-content {
    color: white;
    padding: 15vh 1vw 5rem 1vw;
    text-align: center;
    height: 100vh;

    h1 {
      font-weight: 300;
      font-size: 3vh;
      padding: 0.7rem;
    }

    img {
      width: 70vw;
      max-width: 400px;
      height: auto;
      display: block;
      margin: auto;
      padding: 0.7rem 0;
    }
  }

  @media (max-width: 768px) {
    .background-video {
      opacity: 0%;
      overflow-x: hidden;
    }

    .hero-content {
      background: url(./assets/binarybackground.svg) no-repeat center
        center/cover;
    }
  }

  .about {
    p {
      text-align: justify;
    }
  }

  .row {
    display: flex;
    flex-wrap: wrap;

    .col {
      flex: 1;

      &:last-child {
        margin-left: 1em;
      }

      @media (max-width: 472px) {
        &:last-child {
          margin-left: 0;
        }
      }
    }
  }

  input {
    position: absolute;
    opacity: 0;
    z-index: -1;
  }

  /* Accordion styles */
  .tabs {
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 4px -2px rgba(0, 0, 0, 0.5);
  }

  @media (max-width: 472px) {
    .col1 {
      border-bottom-right-radius: 0;
      border-bottom-left-radius: 0;
    }
    .col2 {
      border-top-left-radius: 0;
      border-top-right-radius: 0;
    }
  }

  .tab {
    width: 100%;
    color: white;
    overflow: hidden;
    text-align: left;

    &-label {
      display: flex;
      justify-content: space-between;
      padding: 1em;
      background: lighten(#001358, 11%);
      font-weight: bold;
      cursor: pointer;

      /* Icon */
      &:hover {
        background: lighten(#001358, 15%);
      }

      &::after {
        content: "\276F";
        height: 1em;
        transition: all 0.35s;
        padding: 0 0 0 1em;
      }
    }

    &-content {
      max-height: 0;
      padding: 0 1em;
      color: var(--light-color);
      background: lighten(#001358, 6%);
      transition: all 0.35s;
    }

    &-close {
      display: flex;
      justify-content: flex-end;
      padding: 1em;
      font-size: 0.75em;
      background: var(--black-color);
      cursor: pointer;

      &:hover {
        background: lighten(#001358, 15%);
      }
    }
  }

  // :checked
  input:checked {
    + .tab-label {
      background: lighten(#001358, 15%);

      &::after {
        transform: rotate(90deg);
      }
    }

    ~ .tab-content {
      max-height: 100vh;
      padding: 1em;
    }
  }

  .calendar-container-container {
    & > * {
      margin-bottom: 10vh;
    }
  }

  @media (max-width: 767px) {
    .hide {
      display: none; 
    }
  }
</style>
