<script lang="ts">
	import ImageGallery from "./ImageGallery.svelte";

    export let projectTitle: string;
    export let projectImages: string[] = [];
    export let anchor: string = "";
</script>
<main id="{anchor}">
    <h1>{projectTitle}</h1>
    <div>
        {#if projectImages.length > 0}
            <ImageGallery images={projectImages} />
        {/if}
        <article><slot></slot></article>
    </div>
</main>
<style>
    main {
        border: dashed 2px var(--canary);
        border-radius: 25px;
        padding: 10px;
        backdrop-filter: blur(5px);
    }
    div {
        width: 100%;
        display: grid;
        grid-template-columns: 1fr 2fr;
        gap: 10px;
    }

    article {
        padding: 10px;
        border: dashed 2px var(--canary);
        border-radius: 20px;
        font-size: 1.5rem;
    }
    article:first-child {
        grid-column: 1 / span 2;
    }
</style>