<script lang="ts">
    let iters = ["", ""]
</script>

<div class="scroller">
    <ul class="scroller-inner">
        {#each iters as iter}
            <li><img src="/src/lib/assets/svg/nodejs.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/mongodb.svg" class="stack-logo" alt="node" width="64" height="32"></li>
            <li><img src="/src/lib/assets/svg/postgresql.svg" class="stack-logo" alt="node" width="50" height="32"></li>
            <li><img src="/src/lib/assets/svg/react.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/svelte.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/javascript.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/html.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/css.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/mongoose.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/sequelize.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/python.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/php.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/docker.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/aws.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/azure.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/nextjs.svg" class="stack-logo" alt="node" width="32" height="32"></li>
            <li><img src="/src/lib/assets/svg/sqlite.svg" class="stack-logo" alt="node" width="64" height="32"></li>
            <li><img src="/src/lib/assets/svg/ansible.svg" class="stack-logo" alt="node" width="32" height="32"></li>  
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
        gap: 4rem;
        animation: scroll 22s linear infinite;
    }

    .stack-logo {
        filter: grayscale(1);
    }

    @keyframes scroll {
        to {
            transform: translate(calc(-50% - 2rem))
        }
    }
</style>