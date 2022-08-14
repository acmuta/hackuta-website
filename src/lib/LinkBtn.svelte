<script>
    export let href = ""
    export let hoverColor = "#001358";
    export let newTab = true;
    $:  color = hoverColor;
</script>

<a {href} target={newTab ? "_blank": ""}><slot></slot></a>

<style lang="scss">
    a {
        margin: 1.3rem;
        font-weight: 600;
        padding: 1.3rem;
        border-radius: 20px;
        border: 2px solid white;
        color: white;
        text-decoration: none;
        display: inline-block;
        font-size: 1.2rem;
        transition: background .5s, color .5s;
        &:hover {
            background: white;
            color: #001358;
        }
    }

</style>