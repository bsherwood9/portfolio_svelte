<script>
</script>

<style>
    section {
        margin-top: 100px;
        padding-top: 60px;
        margin-bottom: 40px;
        font-family: Ubuntu, sans-serif;
        display: flex;
        flex-direction: column;
        font-size: 2rem;
    }
    .title {
        font-size: 4rem;
        text-align: center;
    }
    h1 {
        color: #103784;
        margin: 0;
    }
    div {
        width: 30%;
    }
    .stories {
        width: 100%;
        display: flex;
        justify-content: space-around;
    }
    img {
        width: 270px;
        clip-path: polygon(
            25% 0%,
            75% 0%,
            100% 50%,
            75% 100%,
            25% 100%,
            0% 50%
        );
    }
    .image-shack {
        text-align: center;
    }
    hr {
        height: 3px;
        width: 30%;
        border: none;
        background: linear-gradient(to right, #ffffff, #103784, #ffffff);
        margin-bottom: 30px;
    }

    @media (max-width: 835px) {
        .stories {
            flex-direction: column;
            align-items: center;
        }
        div {
            width: 60%;
            margin-bottom: 30px;
        }
    }
</style>

<section id="about">
    <h1 class="title">About Me</h1>
    <hr />
    <div class="stories">
        <div>
            <h1>Where I am</h1>
            <p>
                I've been working as a QA Engineer at an international software
                company for about 2.5 years. This is my first role in tech and I
                love many things about my position: I work in an exciting
                industry, I get to help create solutions that matter to people,
                and I am always learning. But I want more. I enrolled in Lambda
                School's Fullstack Developer program because I want to create
                solutions to address the issues I find.
            </p>
        </div>
        <div class="image-shack">
            <!-- <h1>Where I've been</h1>
            <p>
                I graduated from University with a Bachelor's Degree in
                Political Science and a minor in Russian and international
                Diplomacy. I had dreams to travel.
            </p>
            <hr /> -->

            <img src="../images/profile.jpeg" alt="A picture of me" />
        </div>
        <div>
            <h1>Where I'm going</h1>
            <p>
                I am going to become a Fullstack Developer. I love building
                things and seeing products take shape. I also love finding bugs
                and seeing those bugs fixed. So I'm looking for my first dev
                role now. I want to be part of an ambitious team, where learning
                and growth are emphasized. Really excited to get going on this
                journey.
            </p>
        </div>
    </div>
</section>
