<script lang="ts">
    import { goto } from "$app/navigation";

    export let id: string

    function handleClick() {
        goto(`#${id}`, { replaceState: true, noScroll: false })
    }

</script>

<div class="arrow-down" tabindex="0" role="button" on:keydown on:click={handleClick}>
    <img src="/src/lib/assets/images/arrow-down.png" alt="arrow down">
</div>

<style>
    .arrow-down {
        position: absolute;
        bottom: 2.5rem;
        right: -5rem;
        width: 32px;
        height: 32px;
        cursor: pointer;
        animation: bounce 1s infinite;
    }

    img {
        width: 100%;
        height: 100%;
    }

    @keyframes bounce {
        0%, 100% {
            transform: translateY(0);
        }

        50% {
            transform: translateY(-5px);
        }
    }

    @media (max-width: 1200px) {
        .arrow-down {
            display: none;
        }
    }
</style>