<script lang="ts">
    import Seo from '$lib/components/Seo.svelte';
</script>

<Seo
    title="Contact"
    description="Get help with Syl, report a bug, or send feedback."
/>

<main>
    <h1>Contact</h1>

    <p>
        Need help with Syl, found a bug, or have an idea for a feature? Send an email
        and I'll get back to you as soon as I can.
    </p>

    <a class="email" href="mailto:contact@getsyl.app">contact@getsyl.app</a>
</main>

<style>
    main {
        padding: 3rem 1rem;
        max-width: 60ch;
        line-height: 1.5;
    }

    .email {
        display: inline-block;
        margin: 1rem 0;
        font-family: 'Momo Trust Display', sans-serif;
        font-size: 1.35rem;
        line-height: 1.3;
        color: #e8e9ed;
        text-decoration: none;
        overflow-wrap: anywhere;

        background-image: linear-gradient(#8fb374, #8fb374);
        background-repeat: no-repeat;
        background-position: 0 100%;
        background-size: 100% 2px;
        padding: 0 0.1em 0.05em;
        transition: background-size 0.25s ease, color 0.25s ease;
    }

    .email:hover,
    .email:focus-visible {
        background-size: 100% 100%;
        color: #0b0b0d;
    }

    @media (prefers-reduced-motion: reduce) {
        .email {
            transition: none;
        }
    }
</style>
