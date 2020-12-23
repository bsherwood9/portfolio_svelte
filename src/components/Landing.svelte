<script>
    import Navigation from "../components/Navigation.svelte";
    import { fade } from "svelte/transition";
    let images = [
        "../images/space.jpeg",
        "../images/forest.jpeg",
        "../images/coding.jpeg",
        "../images/nightsky.jpeg",
        "../images/typing.jpeg",
        "../images/lights.jpeg",
    ];
    let count = 0;
    setInterval(() => {
        // index = (index + 1) % carouselPhotos.length;
        count = (count + 1) % images.length;
    }, 5000);
    //     let imge = root.querySelector(".left-side");
    //     startImages(imge);
    // });
    // let displayImage = (el, x) => {
    //     el.setAttribute("src", images[x]);
    // };
    // function startImages(el) {
    //     let x = 0;
    //     displayImage(el, x);
    //     setInterval(() => {
    //         if (x + 1 === images.length) {
    //             x = 0;
    //         } else {
    //             x++;
    //         }
    //         console.log(x);
    //         displayImage(el, x);
    //     }, 3000);
</script>

<style>
    .main-container {
        font-family: "Ubuntu", sans-serif;
        /* font-family: "Montserrat", sans-serif; */
        position: relative;
        width: 100%;
        max-width: 1200px;
        height: 750px;
        margin: 80px auto;
        z-index: 4;
    }
    .main-container:hover .right-side {
        transform: translate(-10px, -100px);
    }

    p {
        font-size: 6rem;
        color: black;
        margin: 0;
        text-align: center;
    }
    .fullstack {
        padding-top: 30px;
        font-size: 3rem;
        color: #103784;
    }

    .right-shadow {
        filter: drop-shadow(12px 4px 8px rgba(0, 0, 0, 0.3));
        z-index: 80;
    }

    .left-shadow {
        position: relative;
        z-index: 999;
        filter: drop-shadow(12px 6px 6px rgba(0, 0, 0, 0.5));
    }

    .right-side {
        background-color: white;
        right: 0;
        position: absolute;
        z-index: 80;
        width: 50%;
        height: 650px;
        margin-top: 30px;
        color: white;
        clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 30% 100%);
        text-align: center;
        transition: all 0.8s ease-in;
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }

    .left-side {
        position: absolute;
        /* background: black; */
        height: 750px;
        z-index: 1;
        width: 65%;
        clip-path: polygon(0% 0%, 77% 0%, 100% 100%, 0% 100%);
    }

    button {
        font-size: 2.5rem;
        padding: 10px 20px;
        border: none;
        background: hsla(220, 78%, 29%, 1);

        cursor: pointer;
        position: absolute;
        z-index: -5;
        bottom: 80px;
        margin: 0;
        right: 100px;
    }
    button a {
        color: white;
        text-decoration: none;
    }
    img {
        position: absolute;
        width: 100%;
        height: 100%;
        object-fit: cover;
        /* transition: all 0.3s ease-in; */
    }
    .text-container {
        width: 80%;
    }

    @media (max-width: 1200px) {
        .main-container {
            width: 90%;
        }
        .main-container:hover .right-side {
            transform: translate(-10px, -100px);
        }
    }
    @media (max-width: 1024px) {
        p {
            font-size: 4.5rem;
        }
        .fullstack {
            padding-top: 20px;
            font-size: 2.5rem;
            color: #103784;
        }
    }
    @media (max-width: 835px) {
        .main-container {
            width: 90%;
            height: 600px;
        }
        .left-side {
            height: 350px;
            z-index: 1;
            width: 100%;
            clip-path: polygon(-1% 0%, 100% 0%, 100% 85%, 0% 100%);
        }
        .right-side {
            transform: none;
            height: 400px;
            width: 90%;
            bottom: -630px;
            right: 5%;
            clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 11% 100%);
        }
        button {
            bottom: 20px;
            margin: 0;
            left: 40%;
            z-index: 99;
        }
        .text-container {
            transform: translate(-20px);
        }
        .main-container:hover .right-side {
            transform: translate(0px);
        }
    }
</style>

<div class="main-container">
    <div class="left-shadow">
        <div class="left-side">
            {#each [images[count]] as src (count)}
                <img
                    transition:fade={{ y: 200, duration: 3000 }}
                    alt="series of images"
                    {src} />
            {/each}
        </div>
    </div>
    <div class="right-shadow">
        <div class="right-side">
            <div class="text-container">
                <p>BRETT</p>
                <p>SHERWOOD</p>
                <p class="fullstack">-Fullstack Developer-</p>
            </div>
        </div>
    </div>
    <button><a href="#about">Continue</a></button>
</div>
