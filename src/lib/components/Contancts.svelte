<script lang="ts">
    import Toast from "$lib/util-components/Toast.svelte";

    let email = "giorgii.shagidze@gmail.com"
    let show = false
    function handleEmailClick() {
        navigator.clipboard.writeText(email)
        show = true
        setTimeout(() => show = false, 800)
    }
</script>

<section id="contacts" class="contacts">
    <p>Get in Touch</p>
    <h2>Contact Me</h2>

    <div class="contacts-container">
        <div class="email">
            <img src="/src/lib/assets/svg/email.svg" alt="email" width="30" height="30">
            <div  role="button" tabindex="0" on:keydown on:click={handleEmailClick}>{email}</div>
        </div>

        <div class="linkedin">
            <img src="/src/lib/assets/svg/linkedin.svg" alt="linkedin" width="30" height="30">
            <a href="https://www.linkedin.com/in/giorgi-shagidze-716623218/" target="_blank">Linkedin</a>
        </div>
    </div>

    <Toast {show}/>
</section>

<style>
    .contacts {
        height: 70vh;
        padding-top: 4vh;
        margin: 0 10rem;
        box-sizing: border-box;
    }

    .contacts p {
        text-align: center;
        color: rgb(85, 85, 85);
        margin: 0;
    }

    .contacts h2{
        text-align: center;
        font-size: 3rem;
        margin: 0;
    }

    .contacts-container {
        display: flex;
        justify-content: space-around;
        max-width: 500px;
        padding: 29px 10px;
        border: 0.1rem solid rgb(163, 163, 163);
        border-radius: 2rem;
        margin: 2rem auto;
    }

    .email,
    .linkedin {
        display: flex;
        align-items: center;
    }

    .email div {
        font-weight: 400;
        color: #000;
        margin-left: 5px;
        font-size: 1.2rem;
        cursor: pointer;
        transition: all 0.30s;
        text-decoration: none;
        text-decoration-color: #fff;
    }

    .linkedin a {
        margin-left: 5px;
        text-decoration: none;
        text-decoration-color: #fff;
        color: #000;
        font-size: 1.2rem;
        transition: all 0.30s ease;
    }

    .email div:hover,
    .linkedin a:hover {
        color: grey;
        text-decoration: underline;
        text-underline-offset: 1rem;
    }

    @media (max-width: 1200px) {
        .contacts {
            margin: 0 5%;
            height: fit-content;
        }
    }

    @media (max-width: 600px) {
        .contacts h2 {
            font-size: 2rem;
        }

        .contacts-container {
            flex-direction: column;
            align-items: center;
            gap: 8px;
            padding: 14px 10px;
        }

        .email div,
        .linkedin a {
            font-size: 1rem;
        }
    }
</style>