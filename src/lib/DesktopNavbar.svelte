<script>
    import { fade } from 'svelte/transition';
    import hackLogo from '../assets/logo.png'
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
    <nav>
        {#each links as link}
            <a href={link.url}>{link.name}</a>
        {/each}
    </nav>
</header>

<style lang="scss">
    header {
        background: rgba(0, 19, 88, var(--opacity));
        position: fixed;
        top: 0;
        padding: 1.6rem;
        width: 100%;
        text-align: right;
        .navLogo {
            width: 10vw;
            float: left;
        }
        nav {
            margin-right: calc(min(5vw,50px) + 100px);
        }
        a {
            color: white;
            display: inline-block;
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
    @media only screen and (max-width: 600px) {
        header {
            display: none;
        }
    }
</style>