<script lang="ts">
    export let show = false
</script>

<div class:show={show}>
    <slot>
        &#x2714; copied
    </slot>
</div>

<style>
    div {
        position: fixed;
        right: 35px;
        bottom: -50px;
        background-color: #000;
        color: #fff;
        padding: 5px 15px;
        border-radius: 2rem;
        transition: all 0.30s linear;
        z-index: 9;
    }

    .show {
        bottom: 30px;
    }
</style>