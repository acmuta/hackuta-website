<script>
    export let id = "";
    export let accented = false;
</script>

<div class="page" {id} class:accented>
    <slot name="heading"></slot>
    <div class="inner">
        <slot name="content"></slot>
    </div>
</div>

<style lang="scss">
    .page {
        padding: 3rem;
        text-align: center;
        > .inner {
            margin-left: 7rem;
            margin-right: 7rem;
        }
    }
    .accented {
        background: #ff1199;
        color: white;
    }
</style>