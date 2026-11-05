<script lang="ts">
    import Seo from '$lib/components/Seo.svelte';
</script>

<Seo
    title="Syl Privacy Policy"
    description="Privacy policy for the Syl expense tracking app."
/>

<main>
    <h1>Syl Privacy Policy</h1>

    <p>Last updated: November 5, 2026</p>

    <p>
        Syl stores your financial data on your devices and automatically syncs it with
        your private iCloud storage when available. Your expenses are never sent to the developer. Syl does not
        sell your data, show advertisements, or use your financial data for advertising
        or profiling.
    </p>

    <h2>Your expense data</h2>

    <p>
        Expenses, budgets, tags, recurring rules, and settings are stored on
        your device. Syl can also send spending summaries to your paired Apple Watch
        for display in the Watch app and its widgets, independently of iCloud Sync.
    </p>

    <p>
        Receipt scanning uses Apple's on-device text recognition and Apple Intelligence
        features. Receipt images and recognized text are not uploaded to the developer
        or an external receipt-processing service. Information you save from a receipt
        is treated like any other expense.
    </p>

    <p>
        Smart Tagging suggests a tag for a new expense by reading its name with Apple's
        on-device language model. Suggestions are generated on your device, and the
        expense name isn't sent to the developer or another service. You can choose how
        Smart Tagging works, or turn it off, in Syl's tag settings.
    </p>

    <h2>Siri, Shortcuts, and Spotlight</h2>

    <p>
        Syl makes your expenses and tags available to Siri, Shortcuts, and Spotlight on
        your device, so you can search for expenses, add them by voice, or ask about your
        budget. Apple stores this search index on your device and handles requests under
        its own <a href="https://www.apple.com/legal/privacy/">privacy policy</a>. Syl updates the
        index when you edit or delete expenses, and removes entries when you delete data.
        Actions that show or change financial data require your device to be unlocked.
    </p>

    <h2>iCloud Sync</h2>

    <p>
        Syl automatically syncs financal data through your private iCloud database
        and supported settings through Apple's iCloud preference storage when available.
        Apple operates iCloud under its own terms and
        <a href="https://www.apple.com/legal/privacy/">privacy policy</a>.
    </p>

    <p>
        You can manage Syl's iCloud access in the Settings app under your Apple Account
        and iCloud. Disabling access or signing out can remove iCloud-synced data from
        this device. Export a backup beforehand if you want a separate copy. Sync may be
        delayed or unavailable while offline, when storage is full, or when iCloud access
        is disabled. Syl's development builds use separate, local-only storage.
    </p>

    <h2>Retention and deletion</h2>

    <p>
        Your saved data remains until you delete it. In Syl's Settings:
    </p>

    <ul>
        <li><em>Delete Expense Data</em> removes expenses, with an option to also remove recurring expense rules.</li>
        <li><em>Delete All Data</em> removes expenses, recurring rules, tags, and preferences.</li>
    </ul>

    <p>
        When iCloud is available, Syl saves local record deletions for synchronization
        and requests removal of synced preferences during Delete All Data. It keeps
        sync enabled so those deletions can propagate. Local completion does not confirm
        that every cloud copy was deleted. Records not yet downloaded to this device
        may remain in iCloud. With iCloud access disabled, cloud copies may return when
        access is restored. Remaining cloud data can be managed separately in your
        Apple Account's iCloud storage settings.
    </p>

    <p>
        Other devices, such as your Apple Watch, may retain older data until they receive
        an update. Removing the iPhone app does not delete iCloud data or copies on other
        devices.
    </p>

    <h2>Imports and exports</h2>

    <p>
        Syl can import files you select and export JSON backups or CSV files to a
        location you choose. Exported files contain readable expense data and are not
        encrypted by Syl. Files saved or shared outside Syl, including original import
        files, must be deleted separately. Deleting data in Syl cannot recall those copies.
    </p>

    <h2>Permissions</h2>

    <p>
        Syl requests camera access for receipt scanning, Photos access so you can pick a
        receipt photo, and notification permission for optional reminders. You can
        change these permissions in iOS Settings and turn reminders off in Syl's
        notification settings.
    </p>

    <p>
        Photos access is optional. If you allow it, Syl shows your photos in a grid so
        you can choose a receipt. You can share your whole library or only the photos you
        select, and change that selection from the grid's <em>Manage</em> menu. The photo you
        choose is read on your device to fill in the expense. Syl doesn't keep a copy of
        it and doesn't upload your photos. If you don't allow Photos access, <em>All Photos</em>
        opens the system photo picker, which shares only the photo you pick.
    </p>

    <h2>Feedback and support</h2>

    <p>
        If you email the developer, your email address, message, and any attachments are
        used to respond and help resolve your request. Syl's feedback email includes
        your app version, iOS version, and device model. You can edit or cancel the
        message before sending it; your expense database is not automatically attached.
    </p>

    <p>
        You can request deletion of support correspondence by emailing <a href="mailto:contact@getsyl.app">contact@getsyl.app</a>.
    </p>

    <h2>This website</h2>

    <p>
        The website displaying this policy, including when opened inside Syl, uses
        Cloudflare Web Analytics to measure page visits and loading performance.
        Cloudflare states that this service does not collect or use visitors' personal
        data. Its documentation describes seven days of unsampled analytics data and
        access to historical analytics for six months. See
        <a href="https://developers.cloudflare.com/web-analytics/faq/">Cloudflare's documentation</a>.
        These website metrics do not include your Syl expense records.
    </p>

    <p>
        The page also loads fonts from Adobe Fonts and Google Fonts, which involves
        requests to Adobe's and Google's servers. These requests can include your IP
        address and browser details. See
        <a href="https://www.adobe.com/privacy/policy.html">Adobe's privacy policy</a> and
        <a href="https://policies.google.com/privacy">Google's privacy policy</a> for their
        data-handling practices.
    </p>

    <h2>Contact</h2>

    <p>
        For privacy questions or requests, send an email to <a href="mailto:contact@getsyl.app">contact@getsyl.app</a>.
    </p>
</main>

<style>
    main {
        padding: 1rem 1rem 4rem;
    }
</style>
