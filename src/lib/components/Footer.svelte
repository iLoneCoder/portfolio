<section class="footer">
    <div>
        <a href="#">Experience</a>
        <a href="#">Projects</a>
    </div>

    <p>Copyright © 2023 Giorgi Shagidze. All Rights Reserved.</p>
</section>

<style>
    .footer {
        height: 26vh;
    }

    .footer div {
        display: flex;
        justify-content: center;
        height: 17vh;
        align-items: center;
        gap: 2rem;
    }

    a {
        font-size: 1.5rem;
        color: #000;
        text-decoration: none;
        text-decoration-color: #fff;
        transition: all 0.30s;
    }

    a:hover {
        color: grey;
        text-decoration: underline;
        text-decoration-color: grey;
        text-underline-offset: 1rem;
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

        .footer div {
            flex-direction: column;
            align-items: center;
        }

        a {
            font-size: 1rem;
        }
    }
</style>