<script>
    export let id = "";
    import binarybackground from '../assets/binarybackground.svg'
    export let accented = false;
    export let special = false;
</script>

<div class="page" {id} class:accented class:special>
    <slot name="heading"></slot>
    <div class="inner">
        <slot name="content"></slot>
    </div>
</div>

<style lang="scss">
    .page {
        padding: 2rem 1rem;
        text-align: center;
        > .inner {
            margin-left: 10vw;
            margin-right: 10vw;
        }
    }
    .accented {
        background: #ff1199;
        color: white;
    }

    .special {
        padding: 1rem;
        background: url(../assets/binarybackground.svg) no-repeat center center/cover;
    }
</style>