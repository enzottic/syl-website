<script lang="ts">
    import appIcon from '$lib/images/app_icon.png';
    import sageHero from '$lib/images/sage_hero.png';
    import Seo from '$lib/components/Seo.svelte';
    import FeatureReceipt from '$lib/components/FeatureReceipt.svelte';

</script>

<Seo
    title="Syl"
    description="A simple expense tracking app for iOS."
    image={sageHero}
/>

<main>
    <div class="hero">
        <div class="hero-text">
            <h1 class="title hero-title">A free expense tracking and budgeting app</h1>
            <p>Coming soon for iOS and iPadOS</p>
            <a href="https://testflight.apple.com/join/RWj66HUZ">
                <text>Download now on TestFlight</text>
            </a>
        </div>

        <div class="hero-image">
            <img src={sageHero} class="responsive-image" alt="syl on ios"/>
        </div>
    </div>

    <section class="features">
        <div class="features-copy">
            <h2 class="features-title">
                Easy expense tracking.
                <span>100% free.</span>
            </h2>
            <p>
                Syl is free. There's no account to create, no subscription, and no ads.
                Your expenses live on your device, and only sync through your own iCloud
                if you turn it on.
            </p>
        </div>

        <FeatureReceipt />
    </section>
</main>

<style>

main {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.hero {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    padding-top: 3rem;
}

.hero-text {
    flex: 1;
    min-width: 0;
    padding: 1rem;
}

.hero-image {
    flex: 1;
    min-width: 0;
    padding: 1rem;
    display: flex;
    justify-content: flex-end;
}

.hero-image .responsive-image {
    width: 100%;
    max-width: 560px;
    height: auto;
}

.title {
    font-size: 3rem;
}

.hero-title {
    margin: 0 0 1rem;
    line-height: 1.15;
}

.features {
    display: flex;
    /* receipt on the left on desktop; copy stays first in the markup so it leads on mobile */
    flex-direction: row-reverse;
    align-items: center;
    justify-content: space-between;
    gap: 4rem;
    padding: 5rem 1rem;
}

.features-copy {
    flex: 1;
    max-width: 32rem;
}

.features-title {
    font-size: 2.75rem;
    line-height: 1.1;
    margin: 0 0 1.5rem;
}

.features-title span {
    display: block;
    color: #8FB374;
}

.features-copy p {
    color: rgba(232, 233, 237, 0.7);
    line-height: 1.6;
    margin: 0;
}

@media (max-width: 1110px) {
    .hero {
        flex-direction: column;
    }

    .hero-text {
        text-align: center;
        order: -1;
    }

    .hero-image {
        justify-content: center;
    }

    .hero-image .responsive-image {
        max-width: 480px;
    }

    .features {
        flex-direction: column;
        gap: 3rem;
        padding: 3rem 1rem;
    }

    .features-copy {
        text-align: center;
    }
}

@media (max-width: 600px) {
    .features-title {
        font-size: 2.1rem;
    }
}
</style>
