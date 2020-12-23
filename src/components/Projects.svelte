<script>
    import { onMount } from "svelte";
    import { fade } from "svelte/transition";

    let tipsease = "images/tipsease.png";
    let airbnb = "images/airbnb.png";
    let conway = "images/conway.png";
    let spider = "images/spidergraph.png";
    let market = "images/market.png";
    let root;
    let card_array;
    let grid;
    let offset = 0;
    let leftBool = true;
    let rightBool = false;
    let wh = window.innerWidth;
    onMount(() => {
        console.log(card_array);
        card_array = root.querySelectorAll(".card");
        grid = root.querySelector(".project-grid");
        // wh = window.innerWidth;
        console.log("window width", wh);
    });

    function handleClick(btn, el) {
        wh = window.innerWidth;
        let offsetChange = 500;
        if (wh <= 520) {
            offsetChange = 380;
        }
        if (btn == "prev") {
            offset += offsetChange;
        }
        if (btn == "next") {
            offset -= offsetChange;
        }
        if (offset === -1520 && wh <= 520) rightBool = true;
        if (offset === -2000 && wh <= 1024 && wh > 520) rightBool = true;
        if (offset === -1500 && wh > 1024) rightBool = true;
        if (offset < 0 && offset > -1500) {
            leftBool = false;
            rightBool = false;
        }
        if (offset === 0) {
            leftBool = true;
        }
        el.style.transform = `translateX(${offset}px)`;
        console.log(grid);
        console.log(offset);
    }
</script>

<style>
    h1 {
        margin: 0;
        font-size: 4rem;
        color: #103784;

        text-align: center;
    }
    h2 {
        margin: 0;
        padding: 20px 10px;
        background: #fff;
        text-align: center;
        font-size: 2.5rem;
        color: #103784;
    }
    section {
        font-family: Ubuntu, sans-serif;
    }
    img {
        width: 100%;
        height: 300px;
        object-fit: fill;
    }
    .project-wrapper {
        /* z-index: -1; */
        position: relative;
        width: 100%;
        padding-bottom: 100px;
        overflow: hidden;
    }
    .project-grid {
        /* z-index: -1; */
        display: flex;
        justify-content: flex-start;
        transform: translateX(5px);
        transition: transform 0.25s ease;
    }
    div.card {
        background: white;
        filter: drop-shadow(4px 2px 4px rgba(0, 0, 0, 0.2));
        margin-right: 10px;
        padding: 10px;
        margin-top: 30px;
        margin-bottom: 30px;
    }
    .card-size {
        width: 470px;
        /* padding: 10px; */
        /* padding: 10px 0; */
    }
    .card div p {
        text-align: left;
        font-size: 2rem;
        color: black;
    }
    .card div p:nth-child(2) {
        font-size: 1.5rem;
    }
    hr {
        height: 3px;
        width: 30%;
        border: none;
        background: linear-gradient(to right, #ffffff, #103784, #ffffff);
    }
    button {
        font-size: 2.5rem;
        padding: 10px 20px;
        border: #fff;
        background: #103784;
        border-radius: 0;
        transition: all 0.3s ease;
    }
    button:hover {
        cursor: pointer;
    }
    .prev {
        border: none;
        padding: 5px;
        border-radius: 50%;
        background: #103784;
        position: absolute;
        z-index: 99;
        top: 50%;
        left: 0;
    }
    .next {
        border: none;
        padding: 5px;
        border-radius: 50%;
        background: #103784;
        position: absolute;
        z-index: 99;
        top: 50%;
        right: 0;
    }

    a {
        color: #fff;
        text-decoration: none;
    }
    svg {
        padding-top: 5px;
    }

    .buttons {
        margin: 0 auto;
        width: 50%;
        display: flex;
        flex-direction: column;
        padding: 10px;
    }
    .desc {
        height: 100%;
        min-height: 150px;
    }
    p {
        padding: 15px 0;
        display: flex;
        justify-content: center;
    }
    .buttons button:hover {
        transform: translate(0, -5px);
    }
    img {
        filter: drop-shadow(4px 2px 4px rgba(0, 0, 0, 0.2));
    }
    @media (max-width: 1024px) {
        .project-wrapper {
            width: 500px;
            margin: 0 auto;
        }
        .project-grid {
            transform: translateX(0px);
        }
        .next {
            top: 22%;
        }
        .prev {
            top: 22%;
        }
    }
    @media (max-width: 520px) {
        .project-wrapper {
            width: 375px;
            margin: 0 auto;
        }
        .project-grid {
            transform: translateX(0px);
        }
        .card-size {
            width: 350px;
        }
        .desc {
            height: 150px;
            /* min-height: 150px; */
        }
        div p:nth-child(2) {
            padding: 0;
            height: 34px;
        }
    }
</style>

<section bind:this={root}>
    <h1>Projects</h1>
    <hr />
    <div class="project-wrapper">
        <div class="project-grid">
            <div class="card">
                <h2>Market Avenue</h2>
                <div class="card-size">
                    <img src={market} alt="website cover" />
                    <div>
                        <p class="desc">
                            Team ecommerce project that pairs local vendors with
                            customers online. Worked with an existing project in
                            which we created a new backend and connected it to
                            an old frontend. Very frustrating project that
                            taught me a lot.
                        </p>
                        <p>
                            React | Nodejs | Context | Express | SQL | Postgres
                            | Knex
                        </p>
                        <div class="buttons">
                            <button><a
                                    href="https://github.com/bsherwood9/quick-street-fe">Frontend</a></button>
                            <button><a
                                    href="https://github.com/bsherwood9/quick-street-be">Backend</a></button>
                        </div>
                    </div>
                </div>
            </div>
            <div class="card">
                <h2>Tip$ease</h2>
                <div class="card-size">
                    <img src={tipsease} alt="website cover" />
                    <div>
                        <p class="desc">
                            One of my first frontend projects. Designed and
                            created all the frontend UI/UX.
                        </p>
                        <p>HTML5 | CSS3</p>
                        <div class="buttons">
                            <button><a
                                    href="https://github.com/Tipsease-Buildweek/Brett-UI">Code</a></button>
                            <button><a
                                    href="https://tipsease-buildweek.github.io/Brett-UI/">Website</a></button>
                        </div>
                    </div>
                </div>
            </div>
            <div class="card">
                <h2>Airbnb Price Optimizer</h2>
                <div class="card-size">
                    <img src={airbnb} alt="website cover" />
                    <div>
                        <p class="desc">
                            Worked with datascience team to design and create an
                            app that allows users to optimize the price of their
                            houses using housing data from Berlin, Germany.
                        </p>
                        <p>React | ContextAPI | Sass | HTML5</p>
                        <div class="buttons">
                            <button><a
                                    href="https://github.com/BuildWeekAirbnbOptimal1/Frontend">Code</a></button>
                            <button><a
                                    href="https://airbnb-price-optimizer.now.sh/">Website</a></button>
                        </div>
                    </div>
                </div>
            </div>
            <div class="card">
                <h2>Conway's Game of Life</h2>
                <div class="card-size">
                    <img src={conway} alt="website cover" />
                    <div>
                        <p class="desc">
                            My first attempt at Conway's Game of Life.
                        </p>
                        <p>Javascript | HTML5 | CSS3</p>
                        <div class="buttons">
                            <button><a
                                    href="https://github.com/bsherwood9/gameOfLifeJS">Code</a></button>
                            <button><a
                                    href="https://game-of-life-js-git-master.bsherwood9.vercel.app/">Website</a></button>
                        </div>
                    </div>
                </div>
            </div>
            <div class="card">
                <h2>SpiderGraph</h2>
                <div class="card-size">
                    <img src={spider} alt="website cover" />
                    <div>
                        <p class="desc">
                            Team project building an app that allows users to
                            create spider graphs with multiple sets of data.
                        </p>
                        <p>React | MaterialUI | ChartJS | Redux</p>
                        <div class="buttons">
                            <button><a
                                    href="https://github.com/Spider-Graph-1/Front-End">Code</a></button>
                            <button><a
                                    href="https://spidergraph.now.sh/">Website</a></button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        {#if leftBool}
            <span />
        {:else}
            <button
                transition:fade
                class="btn prev"
                disabled={leftBool}
                on:click={handleClick('prev', grid)}>
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    version="1.1"
                    width="24"
                    height="24"
                    xml:lang="de">
                    <path
                        style="fill:#fff"
                        d="m 14 1 L 20 1 L 10 12 L 20 23 L 14 23 L 4 12 Z"
                        id="cl" />
                </svg>
            </button>
        {/if}
        {#if rightBool}
            <span />
        {:else}
            <button
                transition:fade
                class="btn next"
                disabled={rightBool}
                on:click={handleClick('next', grid)}>
                <svg
                    xmlns="http://www.w3.org/2000/svg"
                    version="1.1"
                    width="24"
                    height="24"
                    xml:lang="de">
                    <path
                        style="fill:#fff"
                        d="m 4 1 L 10 1 L 20 12 L 10 23 L 4 23 L 14 12 Z"
                        id="cr" />
                </svg>
            </button>
        {/if}
    </div>
</section>
