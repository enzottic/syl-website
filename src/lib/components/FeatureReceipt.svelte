<script lang="ts">
    // Self-hosted so the receipt font doesn't make a third-party request
    import '@fontsource/doto/800.css';
    import '@fontsource/doto/900.css';

    type Line = { item: string; value: string; note?: string };

    const features: Line[] = [
        { item: 'Budgets', value: '0.00', note: 'each expense is a want, a need, or set aside for savings'},
        { item: 'Tags', value: '0.00', note: 'further categorize your expenses' },
        { item: 'Receipt parsing', value: '0.00', note: 'parse receipts with an on-device model' },
        { item: 'iCloud sync', value: '0.00', note: 'optional, tracking your spending across devices' },
        { item: 'Spending stats', value: '0.00', note: 'trends over time' },
        { item: 'Recurring expenses', value: '0.00', note: 'track those subscriptions'},
        { item: 'Home screen widgets', value: '0.00', note: 'monthly summary at a glance' },
        { item: 'JSON & CSV export', value: '0.00', note: 'take your data anywhere' }
    ];

    const notIncluded: Line[] = [
        { item: 'Account', value: 'NONE' },
        { item: 'Subscription', value: 'NONE' },
        { item: 'Ads', value: 'NONE' },
    ];
</script>

<div class="receipt-wrap">
    <article class="receipt" aria-label="Syl features, presented as a receipt">
        <header class="receipt-header">
            <p class="store">syl</p>
            <p>expense tracking &amp; budgeting</p>
            <p>getsyl.app</p>
        </header>

        <div class="meta">
            <span>ORDER #0001</span>
            <span>IPHONE · IPAD</span>
        </div>
        <div class="meta">
            <span>CASHIER: ENZO</span>
            <span>COPY: CUSTOMER</span>
        </div>

        <hr />

        <p class="section-label">Included</p>
        <ul>
            {#each features as line}
                <li>
                    <div class="row">
                        <span class="item">{line.item}</span>
                        <span class="leader" aria-hidden="true"></span>
                        <span class="value">{line.value}</span>
                    </div>
                    {#if line.note}
                        <p class="note">{line.note}</p>
                    {/if}
                </li>
            {/each}
        </ul>

        <hr />

        <p class="section-label">Not included</p>
        <ul>
            {#each notIncluded as line}
                <li>
                    <div class="row">
                        <span class="item">{line.item}</span>
                        <span class="leader" aria-hidden="true"></span>
                        <span class="value">{line.value}</span>
                    </div>
                </li>
            {/each}
        </ul>

        <hr />

        <div class="row">
            <span class="item">Items</span>
            <span class="leader" aria-hidden="true"></span>
            <span class="value">{features.length}</span>
        </div>
        <div class="row">
            <span class="item">Subtotal</span>
            <span class="leader" aria-hidden="true"></span>
            <span class="value">0.00</span>
        </div>
        <div class="row total">
            <span class="item">Total</span>
            <span class="leader" aria-hidden="true"></span>
            <span class="value">FREE</span>
        </div>

        <hr />

        <footer class="receipt-footer">
            <div class="barcode" aria-hidden="true"></div>
        </footer>
    </article>
</div>

<style>
    .receipt-wrap {
        /* drop-shadow instead of box-shadow so the torn edges cast a shadow too */
        filter: drop-shadow(0 24px 40px rgba(0, 0, 0, 0.55));
        width: min(100%, 440px);
    }

    .receipt {
        --paper: #f4f1e9;
        --ink: #1f1d1a;
        --tooth: 14px;

        background: linear-gradient(180deg, #f7f4ed 0%, var(--paper) 60%, #ece8de 100%);
        color: var(--ink);
        font-family: 'Doto', ui-monospace, 'SF Mono', SFMono-Regular, Menlo, Consolas, monospace;
        font-weight: 800;
        font-size: 0.8rem;
        line-height: 1.45;
        letter-spacing: 0.02em;
        padding: calc(var(--tooth) + 1.5rem) 1.75rem calc(var(--tooth) + 1.5rem);

        /* torn edges */
        mask:
            conic-gradient(from 135deg at top, #0000, #000 1deg 89deg, #0000 90deg)
                top / var(--tooth) 51% repeat-x,
            conic-gradient(from -45deg at bottom, #0000, #000 1deg 89deg, #0000 90deg)
                bottom / var(--tooth) 51% repeat-x;
    }

    .receipt p {
        margin: 0;
    }

    .receipt-header {
        text-align: center;
        text-transform: uppercase;
        margin-bottom: 1rem;
    }

    .store {
        font-family: 'Momo Trust Display', sans-serif;
        font-size: 2.4rem;
        line-height: 1;
        text-transform: none;
        margin-bottom: 0.5rem !important;
    }

    .meta {
        display: flex;
        justify-content: space-between;
        gap: 1rem;
        text-transform: uppercase;
    }

    hr {
        border: none;
        border-top: 1.5px dashed var(--ink);
        opacity: 0.5;
        margin: 1rem 0;
    }

    .section-label {
        text-align: center;
        text-transform: uppercase;
        letter-spacing: 0.2em;
        margin-bottom: 0.6rem !important;
    }

    .section-label::before,
    .section-label::after {
        content: ' -- ';
        letter-spacing: 0;
    }

    ul {
        list-style: none;
        margin: 0;
        padding: 0;
        display: flex;
        flex-direction: column;
        gap: 0.35rem;
    }

    .row {
        display: flex;
        align-items: baseline;
        text-transform: uppercase;
    }

    .leader {
        flex: 1;
        min-width: 1.5ch;
        margin: 0 0.6ch;
        border-bottom: 2px dotted var(--ink);
        opacity: 0.35;
        transform: translateY(-0.25em);
    }

    .value {
        white-space: nowrap;
    }

    .note {
        padding-left: 2ch;
        font-size: 0.72rem;
        opacity: 0.6;
    }

    .total {
        font-size: 1.15rem;
        font-weight: 900;
        margin: 0.3rem 0;
    }

    .receipt-footer {
        text-align: center;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 0.3rem;
    }

    .barcode {
        width: 80%;
        height: 48px;
        margin: 0.75rem 0 0.4rem;
        background: repeating-linear-gradient(
            90deg,
            var(--ink) 0 2px,
            transparent 2px 4px,
            var(--ink) 4px 5px,
            transparent 5px 8px,
            var(--ink) 8px 11px,
            transparent 11px 12px,
            var(--ink) 12px 13px,
            transparent 13px 16px
        );
    }

    @media (max-width: 480px) {
        .receipt {
            padding-left: 1.1rem;
            padding-right: 1.1rem;
            font-size: 0.72rem;
        }
    }
</style>
