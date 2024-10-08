<script lang="ts">
    import "../global.css";
    import { onMount } from "svelte";
    import AOS from "aos";
    import 'aos/dist/aos.css';
    import Header from "$lib/components/Header.svelte";

    onMount(()  => {
        AOS.init({
            once: true
        })
    })
</script>

<Header />
<slot/>