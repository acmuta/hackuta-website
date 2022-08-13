<script>
    export let links = [{url:"/", name:"Link 1"}, {url:"/", name: "Link 2"}];
</script>

<header>
    <nav>
        {#each links as link}
            <a href={link.url}>{link.name}</a>
        {/each}
    </nav>
</header>

<style lang="scss">
    header {
        position: fixed;
        top: 0;
        padding: 2rem;
        width: 100%;
        text-align: right;
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
</style>