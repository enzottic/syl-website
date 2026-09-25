<script lang="ts">
    import { page } from '$app/state';
    import logo from '$lib/images/SageLogoBase.png';

    const links = [
        { href: '/contact', label: 'Contact' },
        { href: '/privacy', label: 'Privacy' }
    ];
</script>

<header>
    <a class="brand" href="/" aria-label="Syl home">
        <img src={logo} alt="" />
        <span>syl</span>
    </a>

    <nav aria-label="Main">
        {#each links as link}
            <a
                href={link.href}
                aria-current={page.url.pathname === link.href ? 'page' : undefined}
            >
                {link.label}
            </a>
        {/each}
    </nav>
</header>

<style>
    header {
        display: flex;
        align-items: center;
        justify-content: space-between;
        gap: 1rem;
        padding: 1.5rem 1rem;
    }

    .brand {
        display: flex;
        align-items: center;
        gap: 0.5rem;
        color: inherit;
        text-decoration: none;
        font-family: 'Momo Trust Display', sans-serif;
        font-size: 1.5rem;
    }

    .brand img {
        width: 32px;
        height: auto;
    }

    nav {
        display: flex;
        gap: 1.5rem;
    }

    nav a {
        color: rgba(232, 233, 237, 0.65);
        text-decoration: none;
    }

    nav a:hover,
    nav a[aria-current='page'] {
        color: #e8e9ed;
    }
</style>
