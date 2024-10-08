<script lang="ts">
    import emblaCarouselSvelte from 'embla-carousel-svelte';
    import type { EmblaCarouselType, EmblaEventType } from 'embla-carousel'
    import arrow from "$lib/assets/svg/arrow.svg";
    import Button from '$lib/util-components/Button.svelte';
    import ArrowDown from '$lib/util-components/ArrowDown.svelte';

    let options = { align: "start"}

    let emblaApi: EmblaCarouselType
    let isNextDisabled = false
    let isPrevDisabled = true

    let projects = [
        {
            image: "/src/lib/assets/images/project-1.png",
            alt: "project-1",
            title: "Project one",
            github: ""
        },
        {
            image: "/src/lib/assets/images/project-2.png",
            alt: "project-2",
            title: "Project two",
            github: ""
        },
        {
            image: "/src/lib/assets/images/project-3.png",
            alt: "project-3",
            title: "Project Three",
            github: ""
        },
        {
            image: "/src/lib/assets/images/project-1.png",
            alt: "project-4",
            title: "Project fourth",
            github: ""
        },
        {
            image: "/src/lib/assets/images/project-1.png",
            alt: "project-5",
            title: "Project fifth",
            github: ""
        },
        {
            image: "/src/lib/assets/images/project-1.png",
            alt: "project-6",
            title: "Project sixth",
            github: ""
        }
    ]
    
    function onInit(event: CustomEvent<EmblaCarouselType>): void {
        emblaApi = event.detail
    }

    $: {
        if (emblaApi) {
            emblaApi.on("reInit", handleArrowButtonIsDisabled).on("select", handleArrowButtonIsDisabled)
        }
    }

    function handleArrowButtonIsDisabled() {
        isNextDisabled = !emblaApi.canScrollNext()
        isPrevDisabled = !emblaApi.canScrollPrev()

    }

    function onNextButtonClick() {
        emblaApi.scrollNext()
    }

    function onPrevButtonClick() {
        emblaApi.scrollPrev()
    }
</script>

<section id="projects" class="projects">
    <p data-aos="fade-up" data-aos-duration="800" data-aos-anchor-placement="top-bottom">Browse my projects</p>
    <h2 data-aos="fade-up" data-aos-duration="800" data-aos-anchor-placement="top-bottom">Projects</h2>

    <div class="embla" data-aos="fade-up" data-aos-duration="800" data-aos-anchor-placement="center-bottom"  use:emblaCarouselSvelte="{{ options }}" on:emblaInit={onInit}>
        <div class="embla__container">
            {#each projects as project, index (index)}
                <div class="embla__slide">
                    <div class="project-card">
                        <div class="card-img">
                            <img src={project.image} alt={project.alt}>
                        </div>

                        <div class="card-title">
                            <h3>{project.title}</h3>
                        </div>

                        <div class="card-buttons">
                            <Button border={"light"}>Github</Button>
                        </div>
                    </div>
                </div>
            {/each}
        </div>
    </div>

    <div class="btn-container" data-aos="fade-up" data-aos-duration="800" data-aos-anchor-placement="center-bottom">
        <button on:click={onPrevButtonClick} disabled={isPrevDisabled} style="transform: rotate(-180deg);"><img src={arrow} alt="arrow-left"></button>
        <button on:click={onNextButtonClick} disabled={isNextDisabled}><img src={arrow} alt="arrow-right"></button>
    </div>

    <ArrowDown id={"contacts"}/>
</section>

<style>
    .projects {
        padding-top: 4vh;
        height: 96vh;
        margin: 0 10rem;
        position: relative;
    }

    .projects p {
        text-align: center;
        color: rgb(85, 85, 85);
        margin: 0;
    }

    .projects h2{
        text-align: center;
        font-size: 3rem;
        margin: 0;
    }

    .embla {
        overflow: hidden;
        margin-top: 2rem;
    }
    .embla__container {
        display: flex;
        /* gap: 4%;     */
    }
    .embla__slide {
        flex: 0 0 calc(100%/3); /*30% */
        padding-left: 20px;
        cursor: grab;
        box-sizing: border-box;
    }

    .embla__slide:active {
        cursor: grabbing;
    }

    .project-card {
        border: 1px solid rgb(163, 163, 163);
        border-radius: 2rem;
        padding: 1.5rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        -moz-user-select: none;
   -khtml-user-select: none;
   -webkit-user-select: none;

   /*
     Introduced in Internet Explorer 10.
     See http://ie.microsoft.com/testdrive/HTML5/msUserSelect/
   */
   -ms-user-select: none;
   user-select: none;
    }

    .card-img {
        width: 100%;
        height: 100%;
    }
    
    .card-img img {
        width: 100%;
        height: 100%;
        border-radius: 2rem;
    }

    .card-title h3 {
        font-size: 1.75rem;
        font-weight: 600;
        margin: 16px;
    }

    .btn-container {
        display: flex;
        justify-content: center;
        margin-top: 20px;
        gap: 1rem;
        padding-left: 1rem;
    }

    .btn-container button {
        display: flex;
        padding: 5px;
        border-radius: 50px;
        border:none;
        background-color: #000;
        cursor: pointer;
        transition: background-color 0.15s;
    }

    .btn-container button:hover {
        background-color: #2e2e2e;
    }

    .btn-container button:disabled {
        background-color: #8f8f8f;
        cursor: default;
    }


    @media (max-width: 1200px) {
        .projects {
            margin: 0 5%;
            height: fit-content;
        }

        .embla__slide {
            flex: 0 0 50%;
            padding-left: 16px;
            padding-right: 1px;
        }
    }

    @media (max-width: 650px) {
        .projects {
            margin: 0 4%;
        }
        .embla__slide {
            flex: 0 0 100%;
            padding-left: 5px;
            padding-right: 1px;
        }
    }

    @media (max-width: 600px) {
        .projects h2 {
            font-size: 2rem;
        }
    }

    @media (max-width: 450px) {
        .projects {
            margin: 0 4%;
        }
        .embla__slide {
            flex: 0 0 100%;
            padding-left: 5px;
            padding-right: 5px;
        }

        .btn-container {
            padding-left: unset;
        }
    }



</style>