<script lang="ts">
    import linkedin from "$lib/assets/svg/linkedin.svg";
    import github from "$lib/assets/svg/github.svg";
    import Button from "$lib/util-components/Button.svelte";

</script>

<section class="profile">
    <div class="img-container">
        <picture>
            <source srcset="/src/lib/assets/images/me.webp" type="image/webp">
            <source srcset="/src/lib/assets/images/me.jpg" type="image/jpg">
            <img src="/src/lib/assets/images/me.jpg" alt="me">
        </picture>
    </div>

    <div class="profile-data">
        <p class="profile-text-one">Hello, I'm</p>
        <h1 class="profile-text-title">Giorgi Shagidze</h1>
        <p class="profile-text-two">Fullstack Developer</p>
        
        <div class="btn-container">
            <Button on:click={() => window.open("/src/lib/assets/files/CV_Giorgi_Shagidze.pdf", "_blank")}>Download CV</Button>
            <Button type={"secondary"}>Contact info</Button>
        </div>
        
        <div class="socials-container">
            <a href="https://www.linkedin.com/in/giorgi-shagidze-716623218/" target="_blank">
                <img src={linkedin} alt="linkdin">
            </a>
            <a href="https://github.com/iLoneCoder" target="_blank">
                <img src={github} alt="github">
            </a>
        </div>
    </div>
</section>


<style>
    .profile {
        display: flex;
        justify-content: center;
        gap: 5rem;
        height: 80vh;
    }

    .img-container {
        width: 400px;
        height: 400px;
        margin: auto 0;
    }

    .img-container img {
        width: 100%;
        height: 100%;
        border-radius: 50%;
    }

    .profile-data {
        margin: auto 0;
        text-align: center;
    }

    .profile-text-one {
        color: rgb(85, 85, 85);
        font-weight: 600;
        margin: 0;
    }
    .profile-text-title {
        font-size: 3rem;
        /* background-color: rgb(188, 188, 188); */
        margin: 0;
    }

    .profile-text-two {
        margin: 0 0 1rem 0;
        font-size: 1.75rem;
        color: rgb(85, 85, 85);
        font-weight: 600;
    }

    .btn-container {
        display: flex;
        justify-content: center;
        gap: 1rem;
    }

    .socials-container {
        display: flex;
        justify-content: center;
        gap: 1rem;
    }
    .socials-container img {
        width: 30px;
        margin-top: 1rem;
    }

    @media (max-width: 1200px) {
        .profile {
            /* flex-direction: column;
            align-items: center; */
            display: block;
            padding-top: 4vh;
        }

        .img-container {
            width: 275px;
            height: 275px;
            margin: 10px auto 20px;
        }
    }

    @media (max-width: 600px) {
        .img-container {
            width:unset;
            max-width: 220px;
            height: auto;
            justify-content: center;
        }

        .profile-text-title {
            font-size: 2rem;
        }

        .profile-text-two {
            font-size: 1.25rem;
        }
    }
    
</style>


