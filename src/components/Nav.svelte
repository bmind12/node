<script>
    export let segment;
</script>

<style>
    nav {
        display: flex;
        justify-content: space-between;
        border-bottom: 1px solid rgba(255, 62, 0, 0.1);
        font-weight: 300;
        padding: 0 1em;
    }

    ul {
        display: flex;
        margin: 0;
        padding: 0;
    }

    li {
        display: inline-block;
    }

    [aria-current] {
        position: relative;
        display: inline-block;
    }

    [aria-current]::after {
        position: absolute;
        content: '';
        width: calc(100% - 1em);
        height: 2px;
        background-color: rgb(255, 62, 0);
        display: block;
        bottom: -1px;
    }

    a {
        text-decoration: none;
        padding: 1em 0.5em;
        display: block;
    }
</style>

<nav>
    <ul>
        <li>
            <a
                aria-current={segment === undefined ? 'page' : undefined}
                href=".">
                home
            </a>
        </li>
        <li>
            <a
                aria-current={segment === 'about' ? 'page' : undefined}
                href="about">
                about
            </a>
        </li>

        <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
        <li>
            <a
                rel="prefetch"
                aria-current={segment === 'blog' ? 'page' : undefined}
                href="blog">
                blog
            </a>
        </li>
    </ul>
    <ul>
        <li>
            <a
                aria-current={segment === 'login' ? 'page' : undefined}
                href="login">
                log in
            </a>
        </li>
        <li>
            <a
                aria-current={segment === 'register' ? 'page' : undefined}
                href="register">
                sign up
            </a>
        </li>
    </ul>
</nav>
