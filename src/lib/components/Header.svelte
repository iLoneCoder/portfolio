<script lang="ts">
    import { slide } from "svelte/transition";

    let mobileMenuExtend = false

    function handleHumClick() {
        mobileMenuExtend = !mobileMenuExtend
    }
</script>

<header id="header">
    <div class="desktop-header">
        <div class="logo">
            <a href="/">Home</a>
        </div>
    
        <nav class="nav-container">
            <ul class="nav-list">
                <li><a href="#experience" class="navigation-link">Experience</a></li>
                <li><a href="#projects" class="navigation-link">Projects</a></li>
                <li><a href="#contacts" class="navigation-link">Contact</a></li>
            </ul>
        </nav>
    </div>
    <div class="mobile-header">
        <div class="logo">
            <a href="/">Home</a>
        </div>
        <div class="humburger-menu_container">
            <div class="humburger-icon" role="button" tabindex="0" on:keydown on:click={handleHumClick} on:blur={() => setTimeout(() =>mobileMenuExtend=false, 300)}>
                <span></span>
                <span></span>
                <span></span>
            </div>
            {#if mobileMenuExtend}
                <nav class="mob-nav-container" transition:slide>
                    <ul class="nav-list_mob">
                        <li><a href="#experience">Experience</a></li>
                        <li><a href="#projects">Projects</a></li>
                        <li><a href="#contacts">Contact</a></li>
                    </ul>
                </nav>
            {/if}
        </div>
    </div>
</header>

<style>
    .desktop-header {
        display: flex;
    }

    .mobile-header {
        display: none;
    }

    .desktop-header,
    .mobile-header {
        /* display: flex; */
        justify-content: space-around;
        align-items: center;
        height: 17vh;
    }
    .logo a {
        font-size: 2rem;
        text-decoration: none;
        color: #000;
    }

    .nav-list {
        display: flex;
        justify-content: space-around;
        gap: 2rem;
        list-style-type: none;
        padding: 0;
    }

    .nav-list li a{
        font-size: 1.5rem;
    }

    .humburger-menu_container {
        position: relative;
        cursor: pointer;
    }

    .humburger-icon {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        width: 30px;
        height: 25px;
    }
    .humburger-icon span {
        width: 100%;
        height: 2px;
        background-color: black;
    }

    .mob-nav-container {
        position: absolute;
        margin-top: 5px;
        border: 1px solid black;
        border-radius: 4px;
        width: 7rem;
        text-align: center;
        transform: translateX(-33%);
        background-color: white;
    }

    .nav-list_mob {
        list-style-type: none;
        padding: 0;
    }

    .nav-list_mob a {
        display: block;
        text-decoration: none;
        color: #000;
        font-size: 1.1rem;
        transition: color 0.15s, background-color 0.15s;
    }

    .nav-list_mob a:hover {
        background-color: #000;
        color: #fff;
    }

    @media (max-width: 1200px) {
        .desktop-header {
            display: none;
        }
        .mobile-header{
            display: flex;
        }
    }

    @media (max-width: 768px) {
        .mobile-header .logo a {
            font-size: 1.5rem;
        }
    }

</style>