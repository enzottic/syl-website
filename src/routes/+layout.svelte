<script lang="ts">
	import Header from '$lib/components/Header.svelte';
	import Footer from '$lib/components/Footer.svelte';

	let { children } = $props();
</script>

<div class="container">
    <Header />
    {@render children()}
    <Footer />
</div>

<style>
    :global(html),
    :global(body) {
        width: 100%;
        min-height: 100vh;
        overflow-x: hidden;
        font-family: "proxima-nova", sans-serif;
        font-size: 18px;
    }

    :global(body) {
        background-color: #0b0b0d;
        color: #e8e9ed;
        display: flex;
        justify-content: center;
        margin: 0;
        padding: 0;
    }

    :global(h1),
    :global(h2),
    :global(h3),
    :global(h4),
    :global(h5),
    :global(h6) {
        font-family: "Momo Trust Display", sans-serif;
        font-weight: 400;
    }

    :global(a) {
        color: #c669d8;
    }

    .container {
        width: 70%;
        max-width: 1200px;
        min-width: 0;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
    }

    @media (max-width: 768px) {
        .container {
            width: 90%;
        }
    }

    @media (max-width: 480px) {
        .container {
            width: 94%;
        }
    }
</style>
