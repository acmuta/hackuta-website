<script>
    import { fade } from 'svelte/transition';
    import { Hamburger } from 'svelte-hamburgers';
    let open;


    import hackLogo from '../assets/logo.png';
    export let links = [{url:"/", name:"Link 1"}, {url:"/", name: "Link 2"}];
    let y = 0;
    let windowHeight;
    $: navLogo = (y > windowHeight/2); 
</script>
<svelte:window bind:scrollY={y} bind:innerHeight={windowHeight}/>

<header style:--opacity={Math.min(y/200, 1)}>
    {#if navLogo}
    <img transition:fade="{{duration: 200}}" class="navLogo" src={hackLogo} alt="HackUTA Logo" />
    {/if}
    <Hamburger type="spin" --color=#ff1199  bind:open />
    {#if open}
        {#each links as link}
            <a href={link.url}>{link.name}</a>
        {/each}
    {/if}
</header>

<style lang="scss">
    header {
        background: rgba(0, 19, 88, var(--opacity));
        position: fixed;
        top: 0;
        padding: 1.6rem;
        width: 100%;
        text-align: right;
        font-size: 100%;
        

        .navLogo {
            width: 20vw;
            float: left;
        }

        a {
            color: white;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            text-decoration: none;
            padding: 5px;
            margin: 7px;
            transition: opacity .3s;
            &:hover {
                opacity: .7;
            }
        }
        z-index: 1;
    }
    @media only screen 
    and (min-device-width: 375px) 
    and (max-device-width: 812px) 
    and (-webkit-min-device-pixel-ratio: 3) { 
        header{
            background: rgba(0, 19, 88, var(--opacity));
        }
    }
</style>