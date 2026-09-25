<script lang="ts">
    const year = new Date().getFullYear();
</script>

<footer>
    <p>© {year} Syl · Made by <a href="https://enzottic.me">Enzo</a></p>
    <nav aria-label="Footer">
        <a href="/contact">Contact</a>
        <a href="/privacy">Privacy</a>
    </nav>
</footer>

<style>
    footer {
        margin-top: auto;
        display: flex;
        align-items: center;
        justify-content: space-between;
        flex-wrap: wrap;
        gap: 1rem;
        padding: 2rem 1rem 3rem;
        border-top: 1px solid rgba(255, 255, 255, 0.08);
        color: rgba(232, 233, 237, 0.5);
        font-size: 0.9rem;
    }

    p {
        margin: 0;
    }

    /* inline link within the sentence needs an underline to read as a link */
    p a {
        text-decoration: underline;
        text-decoration-color: rgba(143, 179, 116, 0.6);
        text-underline-offset: 0.2em;
    }

    nav {
        display: flex;
        gap: 1.5rem;
    }

    a {
        color: inherit;
        text-decoration: none;
    }

    a:hover {
        color: #e8e9ed;
    }

    @media (max-width: 480px) {
        footer {
            flex-direction: column-reverse;
            justify-content: center;
        }
    }
</style>
