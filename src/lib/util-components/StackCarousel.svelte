<script lang="ts">
    import nodejs from "$lib/assets/svg/nodejs.svg";
    import mongodb from "$lib/assets/svg/mongodb.svg";
    import postgresql from "$lib/assets/svg/postgresql.svg";
    import react from  "$lib/assets/svg/react.svg";
    import svelte from  "$lib/assets/svg/svelte.svg";
    import javascript from  "$lib/assets/svg/javascript.svg";
    import html from  "$lib/assets/svg/html.svg";
    import css from  "$lib/assets/svg/css.svg";
    import mongoose from  "$lib/assets/svg/mongoose.svg";
    import sequelize from  "$lib/assets/svg/sequelize.svg";
    import python from  "$lib/assets/svg/python.svg";
    import php from  "$lib/assets/svg/php.svg";
    import docker from  "$lib/assets/svg/docker.svg";
    import aws from  "$lib/assets/svg/aws.svg";
    import azure from  "$lib/assets/svg/azure.svg";
    import nextjs from  "$lib/assets/svg/nextjs.svg";
    import sqlite from  "$lib/assets/svg/sqlite.svg";
    import ansible from  "$lib/assets/svg/ansible.svg";

    let iters = ["", ""]
</script>

<div class="scroller">
    <ul class="scroller-inner">
        {#each iters as iter}
            <li><img src={nodejs} class="stack-logo" alt="nodejs" width="32" height="32"></li>
            <li><img src={mongodb} class="stack-logo" alt="mongodb" width="64" height="32"></li>
            <li><img src={postgresql} class="stack-logo" alt="postgresql" width="50" height="32"></li>
            <li><img src={react} class="stack-logo" alt="react" width="32" height="32"></li>
            <li><img src={svelte} class="stack-logo" alt="svelte" width="32" height="32"></li>
            <li><img src={javascript} class="stack-logo" alt="javascript" width="32" height="32"></li>
            <li><img src={html} class="stack-logo" alt="html" width="32" height="32"></li>
            <li><img src={css} class="stack-logo" alt="css" width="32" height="32"></li>
            <li><img src={mongoose} class="stack-logo" alt="mongoose" width="32" height="32"></li>
            <li><img src={sequelize} class="stack-logo" alt="sequelize" width="32" height="32"></li>
            <li><img src={python} class="stack-logo" alt="python" width="32" height="32"></li>
            <li><img src={php} class="stack-logo" alt="php" width="32" height="32"></li>
            <li><img src={docker} class="stack-logo" alt="docker" width="32" height="32"></li>
            <li><img src={aws} class="stack-logo" alt="aws" width="32" height="32"></li>
            <li><img src={azure} class="stack-logo" alt="azure" width="32" height="32"></li>
            <li><img src={nextjs} class="stack-logo" alt="nextjs" width="32" height="32"></li>
            <li><img src={sqlite} class="stack-logo" alt="sqlite" width="64" height="32"></li>
            <li><img src={ansible} class="stack-logo" alt="ansible" width="32" height="32"></li>  
        {/each}

    </ul>
</div>

<style>
    .scroller {
        overflow: hidden;
    }
    .scroller-inner {
        margin: 0;
        width: fit-content;
        list-style-type: none;
        padding-left: 0;
        display: flex;
        gap: 6rem;
        animation: scroll 22s linear infinite;
    }

    .stack-logo {
        filter: grayscale(1);
    }

    @keyframes scroll {
        to {
            transform: translate(calc(-50% - 3rem))
        }
    }
</style>