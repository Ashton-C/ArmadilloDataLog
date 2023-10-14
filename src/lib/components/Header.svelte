<style>
    @font-face {
        font-family:'DM Sans', sans-serif;
        src: url("https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,100;0,9..40,300;1,9..40,300;1,9..40,600&family=Noto+Sans:ital,wght@0,200;0,300;0,400;0,700;1,200;1,500&display=swap");
    }
    header {
        width: 85vw;
        font-size: 1.25rem;
    }
    ul {
        font-family: "Noto Sans", sans-serif;
        display: flex;
        flex-direction: row;
        justify-content: space-evenly;
        align-items: center;
        list-style: none;
    }
    .brand {
        font-family: "DM Sans", sans-serif;
        font-weight: 200;
        font-style: italic;
    }
    a {
        text-decoration: none;
    }
</style>

<header>
    <nav class='nav'>
        <ul>
            <li class='nav_item brand'>
                <a href="/"> DIllO </a>
            </li>
            <li class='nav_item'>
                <a href="/about"> ABOUT </a>
            </li>
            <li class='nav_item'>
                <a href="/contact"> CONTACT </a>
            </li>
        </ul>
    </nav>
</header>