<script lang="ts">
    export let type: "primary" | "secondary" = "primary"
    export let border: "light" | "" = ""
</script>

<button 
    class:primary={type === "primary"}
    class:secondary={type === "secondary"}
    class:light={border === "light"}
    on:click
>
    <slot/>
</button>

<style>
    button {
        font-weight: 500;
        font-size: 0.85rem;
        transition: all 300ms ease;
        padding: 0.80rem 1rem;
        width: 8rem;
        border-radius: 2rem;
        cursor: pointer;
    }

    .primary {
        background-color: transparent;
        border: 1px solid black;
    }

    .secondary {
        background-color: rgb(53, 53, 53);
        color: #fff;
    }

    .primary:hover {
        background-color: black;
        color: #fff;
    }

    .secondary:hover {
        background-color: #000;
    }

    .light {
        border: 1px solid rgb(163, 163, 163);
    }

</style>