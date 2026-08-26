<script lang="ts">
    import { marked } from 'marked';
    import guide from '$lib/docs/guide.md?raw';

    const html = marked(guide, { breaks: true });
</script>

<main class="w-screen h-full flex flex-col gap-4 relative">
        <a href="/" target="" class="fixed top-4 right-4 sm:bottom-10 sm:right-10 bg-red text-white font-bold font-hk rounded-xs px-4 py-2 text-2xl hover:bg-black transition-all duration-300">RETURN</a>

    <div class="markdown-body px-8 sm:px-14 py-6 pb-10 lg:w-[80%] lg:mx-auto">
        {@html html}
    </div>

    <div class="absolute -z-1 top-0 left-0 h-full w-screen opacity-60 select-none">
        <div class="borders absolute top-0 left-0 h-6 w-screen border-b pl-10 text-sm flex items-end ">//MANUFACTURER: HACK CLUB & SOPHIA
        </div>
        <div class="absolute top-0 left-0 h-full w-6 border-r text-sm">
            <div class="borders -rotate-90 translate-y-180 whitespace-nowrap">0x1234 Product ID:DONGLE-YSWS</div>
        </div>
        <div class="absolute top-0 right-0 h-full w-6 border-l">
        </div>
        <div class="absolute bottom-0 left-0 h-6 w-full border-t">
        </div>
    </div>
</main>

<style>
    :global(.markdown-body) {
        font-size: 1rem;
        line-height: 1.5;
        color: inherit;
    }

    :global(.markdown-body h1) {
        font-size: 2rem;
        font-weight: 700;
        margin: 1.5rem 0 1rem;
        border-bottom: 1px solid rgba(128, 128, 128, 0.3);
        padding-bottom: 0.3rem;
    }

    :global(.markdown-body h2) {
        font-size: 1.5rem;
        font-weight: 700;
        margin: 1.5rem 0 0.75rem;
        border-bottom: 1px solid rgba(128, 128, 128, 0.2);
        padding-bottom: 0.25rem;
    }

    :global(.markdown-body h3) {
        font-size: 1.25rem;
        font-weight: 600;
        margin: 1.25rem 0 0.5rem;
    }

    :global(.markdown-body h4) {
        font-size: 1.05rem;
        font-weight: 600;
        margin: 1rem 0 0.5rem;
    }

    :global(.markdown-body p) {
        margin: 0.75rem 0;
    }

    :global(.markdown-body ul),
    :global(.markdown-body ol) {
        margin: 0.75rem 0;
        padding-left: 1.5rem;
    }

    :global(.markdown-body ul) {
        list-style: disc;
    }

    :global(.markdown-body ol) {
        list-style: decimal;
    }

    :global(.markdown-body li) {
        margin: 0.25rem 0;
    }

    :global(.markdown-body li > ul),
    :global(.markdown-body li > ol) {
        margin: 0.25rem 0;
    }

    :global(.markdown-body code) {
        font-family: var(--font-mono);
        background: var(--color-yellow);
        color: var(--color-black);
        padding: 0.1em 0.2em;
        border-radius: 4px;
        font-size: 0.9em;
        font-weight: 700;
    }

    :global(.markdown-body pre) {
        background: var(--color-light-blue);
        border: 1px solid var(--color-light-blue);
        border-radius: 6px;
        padding: 1rem;
        overflow-x: auto;
        margin: 1rem 0;
    }

    :global(.markdown-body pre code) {
        background: none;
        color: var(--color-light-blue)
        padding: 0;
    }

    :global(.markdown-body blockquote) {
        border-left: 3px solid var(--color-yellow);
        padding-left: 1rem;
        margin: 1rem 0;
        color: var(--color-yellow);

    }

    /* --color-blue: #0065D0;
    --color-light-blue: #51E5FF;
    --color-yellow: #FFEF16;
    --color-red: #FE1C1C;
    --color-black: #1c1c1c; */

    :global(.markdown-body a) {
        color: var(--color-light-blue);
        text-decoration: underline;
        text-underline-offset: 2px;
    }

    :global(.markdown-body a:hover) {
        opacity: 0.8;
    }

    :global(.markdown-body img) {
        max-width: 100%;
        border-radius: 6px;
        margin: 1rem 0;
        border: 1px solid var(--color-light-blue);
    }

    :global(.markdown-body hr) {
        border: none;
        border-top: 1px solid var(--color-light-blue);
        margin: 2rem 0;
    }

    :global(.markdown-body table) {
        border-collapse: collapse;
        width: 100%;
        margin: 1rem 0;
        font-size: 0.9rem;
    }

    :global(.markdown-body th),
    :global(.markdown-body td) {
        border: 1px solid var(--color-light-blue);
        padding: 0.5rem 0.75rem;
        text-align: left;
    }

    :global(.markdown-body th) {
        background: var(--color-light-blue);
        color: var(--color-black);
        font-weight: 600;
    }

    :global(.markdown-body details) {
        border: 1px solid var(--color-light-blue);
        border-radius: 6px;
        padding: 0.5rem 1rem;
        margin: 1rem 0;
    }

    :global(.markdown-body summary) {
        cursor: pointer;
        font-weight: 600;
    }

    :global(.markdown-body strong) {
        font-weight: 700;
    }

    :global(.markdown-body em) {
        font-style: italic;
    }
</style>