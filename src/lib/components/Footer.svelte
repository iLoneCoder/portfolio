<script lang="ts">
    import { goto } from "$app/navigation";
    import arrow from "$lib/assets/svg/arrow.svg";

    function handleClick() {
        goto("#header", { replaceState: true, noScroll: false })
    }
</script>


<section class="footer" data-aos="fade-up" data-aos-duration="800" data-aos-anchor-placement="center-bottom">
    <div class="nav">
        <a href="#experience" class="navigation-link">Experience</a>
        <a href="#projects" class="navigation-link">Projects</a>
    </div>
    
    <div class="button-container">
        <button on:click={handleClick}>
            <span class="button-text">Go to the top</span>
            <div class="arrow-container">
                <img src={arrow} alt="arrow-up">
            </div>
        </button>
    </div>

    <p>Copyright © 2023 Giorgi Shagidze. All Rights Reserved.</p>
</section>

<style>
    .footer {
        height: 26vh;
    }

    .nav {
        display: flex;
        justify-content: center;
        height: 12vh;
        align-items: center;
        gap: 2rem;
    }

    a {
        font-size: 1.5rem;
    }

    .button-container {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 5vh;
    }

    .button-container button {
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 0.5rem;

        border: none;
        border-radius: 15px;
        padding-right: 0;
        cursor: pointer;
        transition: all 0.3s ease;
    }

    .button-container button:hover {
        background-color: #000;
        color: #fff;
    }

    .button-container button span {
        font-size: 0.7rem;
    }

    .arrow-container {
        display: flex;
        border: 1px solid #000;
        border-radius: 50px;
        box-sizing: border-box;
        background-color: #000;
    }

    .arrow-container img {
        transform: rotate(-90deg);
    }

    .footer p {
        font-size: 0.7rem;
        color: grey;
        text-align: center;
    }
    
    @media (max-width: 600px) {
        .footer {
            margin: 0 5%;
        }

        .nav {
            flex-direction: column;
            align-items: center;
            gap: 0.5rem;
        }

        a {
            font-size: 1rem;
        }
    }
</style>