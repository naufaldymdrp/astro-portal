<script>
    let isToggled = false;

    function setToggle() {
        isToggled = !isToggled;
        console.log("hello from button");
    }
</script>


<div class="navbar">
    <div class="navbar-head">
        <h1>Astro Portal</h1>
    </div>
    <button class="nav-toggle" on:click={setToggle}>
        <span></span>
    </button>
    <nav class="navbar-nav" class:navbar-nav-toggle={isToggled}>
        <ul>
            <li><a href="/">Home</a></li>
            <li><a>Warehouse Data</a></li>
            <li><a>About</a></li>
            <li><a>Privacy</a></li>
        </ul>
    </nav>
</div>

<style>
    .navbar {
        box-sizing: border-box;
        display: flex;
        background-color: var(--color-primary-light);
        position: fixed;
        width: 100%;
        z-index: 999;
    }


    .navbar-head {
        margin: auto;
    }

    .navbar-nav {
        display: none;
        position: absolute;
        text-align: left;
        top: 100%;
        left: 0;
        width: 100%;
        background-color: var(--color-primary-light);
    }

    .navbar-nav-toggle {
        display: block;
    }

    .navbar-nav ul {
        list-style-type: none;
    }

    .navbar-nav ul li {
        display: block;
        margin-bottom: 10px;
        margin-left: 10px;
    }

    .navbar-nav ul li a, 
    .navbar-nav ul li a:link,
    .navbar-nav ul li a:active,
    .navbar-nav ul li a:hover {
        text-decoration: none;
    }

    .nav-toggle {
        all: unset;
        position: absolute;
        top: 0;
        left: 0;
        cursor: pointer;
        margin-left: 10px;
        height: 100%;
    }

    .nav-toggle span::before,
    .nav-toggle span::after {
        content: '';
        position: absolute;
    }

    .nav-toggle span::after {
        top: 7px;
    }

    .nav-toggle span::before {
        bottom: 7px;
    }

    .nav-toggle span,
    .nav-toggle span::before,
    .nav-toggle span::after {
        display: block;
        position: relative;
        background: black;
        height: 2px;
        width: 2em;
        border-radius: 2px;
    }

</style>
