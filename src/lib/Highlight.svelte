<script lang="ts">
	import ImageGallery from "./ImageGallery.svelte";

    export let projectTitle: string;
    export let projectImages: string[] = [];
    export let anchor: string = "";
    export let fullText: string ="";
</script>
<main id="{anchor}" class="readable-background">
    <div>
        <h1>{projectTitle}</h1>
        {#if fullText !== ""}
            <a href={fullText}>Read More</a>
        {/if}
    </div>
    <div>
        {#if projectImages.length > 0}
            <ImageGallery images={projectImages} />
        {/if}
        <article><slot></slot></article>
    </div>
</main>
<style>
    main {
        border-width: var(--border-width, 0px);
        border-radius: var(--radius, 0px);
        padding: 10px;
    }
    div:first-child {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    div:nth-child(2) {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr 2fr;
        gap: 10px;
    }

    article {
        padding: 10px;
        border-width: var(--border-width, 0px);
        border-radius: var(--radius, 0px);
        font-size: 1.25rem;
        overflow: scroll;
    }
    article:first-child {
        grid-column: 1 / span 2;
    }
    a {
        font-size: 1.5rem;
        color: var(--color-four);
    }

    @media (max-width: 768px) {
        div:nth-child(2) {
            display: flex;
            flex-direction: column-reverse;
            align-items: center;
        }
    }
</style>