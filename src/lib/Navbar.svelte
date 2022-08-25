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
<a id="mlh-trust-badge" style="display:block;max-width:100px;min-width:60px;position:fixed;right:min(5vw,50px);top:0;width:10%;z-index:10000" href="https://mlh.io/na?utm_source=na-hackathon&utm_medium=TrustBadge&utm_campaign=2023-season&utm_content=white" target="_blank"><img src="https://s3.amazonaws.com/logged-assets/trust-badge/2023/mlh-trust-badge-2023-white.svg" alt="Major League Hacking 2023 Hackathon Season" style="width:100%"></a>
{#if header}
  <header style:--opacity={Math.min(Math.max(0, y / 200 - 3), 0.35)}>
    <div style="display: flex">
      <Hamburger type="spin" --color="#ff1199" bind:open />
      <div class="headTop">
        <img
          transition:fade={{ duration: 200 }}
          class="navLogo"
          src={hackLogo}
          alt="HackUTA Logo"
        />
      </div>
    </div>
    
    {#if open}
      {#each links as link}
        <a href={link.url}>{link.name}</a>
      {/each}
    {/if}
  </header>
{/if}

<style lang="scss">
  header {
    //display: flex;
    background: rgba(0, 19, 88, var(--opacity));
    -webkit-backdrop-filter: blur(15px);
    backdrop-filter: blur(15px);
    filter: contrast(1.5);
    position: fixed;
    top: 0;
    padding: 1rem;
    width: 100%;
    text-align: left;
    font-size: 100%;
    .headTop {
      display: flex;
    }

    .hamburger {
      opacity: var(--opacity);
    }

    .navLogo {
      width: 40vw;
      max-width: 175px;
      
      padding: 0.5vh;
      //margin-left: calc(50% - (min(175px, 40vw)/2));
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
      background: rgba(0, 19, 88, var(--opacity));
      -webkit-backdrop-filter: blur(15px);
      backdrop-filter: blur(15px);
      filter: contrast(1.5);
    }
  }

  @media only screen and (min-width: 600px) {
    header 
    {
      display: none;
    }
  }
</style>
