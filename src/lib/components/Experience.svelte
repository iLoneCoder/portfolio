<script lang="ts">
    let frontendTechs = [
        {
            name: "HTML",
            level: "Experienced"
        },
        {
            name: "CSS",
            level: "Experienced"
        },
        {
            name: "SASS",
            level: "Experienced"
        },
        {
            name: "Javascript",
            level: "Experienced"
        },
        {
            name: "React",
            level: "Experienced"
        },
        {
            name: "Sveltekit",
            level: "Experienced"
        },
    ]

    let backendTechs = [
        {
            name: "NodeJS",
            level: "Experienced"
        },
        {
            name: "Sequelize",
            level: "Experienced"
        },
        {
            name: "Mongoose",
            level: "Experienced"
        },
        {
            name: "Postgres",
            level: "Experienced"
        },
        {
            name: "Python",
            level: "Intermediate"
        },
        {
            name: "Selenium",
            level: "Experienced"
        },
    ]
</script>


<section class="experience">
    <p>Explore My</p>
    <h2>Experience</h2>
    <div >

    </div>
    <div class="experience-container">
        <div class="details">
            <h2>Frontend stack</h2>
            <div class="tech-stack-box">
                {#each frontendTechs as frontendTech, index (index)}
                    <div class="tech">
                        <img src="/src/lib/assets/images/checkmark.png" alt="checkmark" class="icon">
                        <div>
                            <h3>{frontendTech.name}</h3>
                            <p>{frontendTech.level}</p>
                        </div>
                    </div>
                {/each}
            </div>
        </div>

        <div class="details">
            <h2>Backend stack</h2>
            <div class="tech-stack-box">
                {#each backendTechs as backendTech, index (index)}
                    <div class="tech">
                        <img src="/src/lib/assets/images/checkmark.png" alt="checkmark" class="icon">
                        <div>
                            <h3>{backendTech.name}</h3>
                            <p>{backendTech.level}</p>
                        </div>
                    </div>
                {/each}
            </div>
        </div>
    </div>
</section>


<style>
    .experience {
        padding-top: 4vh;
        height: 96vh;
        margin: 0 10rem;
    }

    .experience p {
        text-align: center;
        color: rgb(85, 85, 85);
        margin: 0;
    }

    .experience h2{
        text-align: center;
        font-size: 3rem;
        margin: 0;
    }

    .experience-container {
        display: flex;
        gap: 2rem;
        margin-bottom: 2rem;
        margin-top: 2rem;
    }
    
    .details {
        flex: 1;
        border: 1px solid rgb(163, 163, 163);
        border-radius: 2rem;
        padding: 2.5rem;
    }

    .details h2 {
        color: rgb(85, 85, 85);
        font-weight: 600;
        font-size: 1.75rem;
        margin-top: 0;
        margin-bottom: 2rem;
    }

    .tech-stack-box {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-around;
        gap: 2.5rem;
       
    }
    
    .tech {
        display: flex;
        width: 10rem;
        justify-content: space-around;
        gap: 0.5rem;
    }

    .tech h3,
    .tech p {
        margin: 0;
    }

    .tech h3 {
        font-size: 1.17rem;
    }

    .icon {
        height: 2rem;
    }

    @media (max-width: 1200px) {
        .experience {
            margin: 0 5%;
            height: fit-content;
        }
    }

    @media (max-width: 768px) {
        .experience-container {
            flex-direction: column;
            flex-wrap: wrap;
        }
    }

    @media (max-width: 600px) {
        .experience h2 {
            font-size: 2rem;
        }

        .details h2 {
            font-size: 1.25rem;
        }
    }
</style>