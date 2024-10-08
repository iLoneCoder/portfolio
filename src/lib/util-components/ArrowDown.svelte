<script lang="ts">
    import { goto } from "$app/navigation";
    import arrow from "/src/lib/assets/images/arrow-down.png";

    export let id: string

    function handleClick() {
        goto(`#${id}`, { replaceState: true, noScroll: false })
    }

</script>

<div class="arrow-down" data-aos="fade-up" data-aos-duration="800" data-aos-anchor-placement="top-bottom" tabindex="0" role="button" on:keydown on:click={handleClick}>
    <img src={arrow} alt="arrow down">
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