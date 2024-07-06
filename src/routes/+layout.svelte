<header>
    <nav>
        <a class="ref" href="/">home</a>
        <a style="left: 140px" class="ref" href="/about">about me</a>
        <a style="left: 320px" class="ref" href="/projects">projects</a>
        <a style="left: 470px" class="ref" href="/links">links</a>
        <a style="left: 600px" class="ref" href="/image">image</a>
    </nav>
</header>
<style>
    :global(body) {
        background-color: #222222;
        color: white;
        font-family: sans-serif;
        font-weight: bold;
        font-size: 30px;
        line-height: 150%;
    }
    .ref {
        color: white;
        text-decoration: none;
        position: absolute;
        top: 400px;
    }
    .ref:hover {
        color: #0084FF;
    }
</style>
<main>
    <slot></slot>
</main>

<footer>
    <p style="position: absolute; top: 450px">Matvey's website</p>
</footer>
