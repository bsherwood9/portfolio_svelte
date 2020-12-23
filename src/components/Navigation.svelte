<script>
    let contact = "images/envelope-regular.svg";
    let resume = "images/file-regular.svg";
    let brief = "images/briefcase-solid.svg";
    let user = "images/user-circle.svg";
</script>

<style>
    .wrapper {
        max-width: 1200px;
        position: relative;
        z-index: 999;
    }
    div {
        /* transform: translateZ(0); */
        position: fixed;
        z-index: 99;
        top: 100px;
    }

    ul {
        display: flex;
        flex-direction: column;
        width: 50px;
        margin-top: 5px;
        padding: 0;
    }

    li {
        font-family: Ubuntu, sans-serif;
        list-style-type: none;
        text-align: center;
        margin: 5px 0;

        border-radius: 10px;
        transition: all 0.2s ease-in;
    }
    li:hover {
        transform: translate(-5px, -10px) scaleZ(1.1);
        box-shadow: 0px 20px 15px -10px rgba(0, 0, 0, 0.2);
    }
    a {
        position: relative;
        display: block;
        width: 40px;
        height: 40px;
        padding: 10px;
        background: rgb(16, 55, 132);
        color: white;
        border-radius: 10px;
    }
    .resume img {
        padding-left: 4px;
    }

    @media (min-width: 1200px) {
        div {
            right: 5%;
        }
    }

    @media (max-width: 1199px) {
        div {
            right: 300px;
            top: 0;
        }
        ul {
            flex-direction: row;
            justify-content: space-between;
        }
        li {
            margin-top: 10px;
            margin-right: 20px;
        }
    }
</style>

<div class="wrapper">
    <div>
        <ul>
            <li>
                About<a href="#about"><img src={user} alt="User Icon" /></a>
            </li>
            <li>
                Contact<a href="#contact"><img
                        src={contact}
                        alt="Contact envelope" /></a>
            </li>
            <li>
                Portfolio<a href="#tech"><img src={brief} alt="Breifcase" /></a>
            </li>

            <li>
                Resume
                <a
                    href="https://drive.google.com/file/d/1bMUakiZZPg3Co6oAYC62wmW0-ho11q1x/view?usp=sharing"
                    class="resume"><img src={resume} alt="File icon" /></a>
            </li>
        </ul>
    </div>
</div>
