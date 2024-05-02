<script lang="ts">
	import ImageGallery from "./ImageGallery.svelte";

    export let projectTitle: string;
    export let projectImages: string[] = [];
</script>
<main class="readable-background">
    <h1>{projectTitle}</h1>
    <div class="outer">
        {#if projectImages.length > 0}
            <ImageGallery images={projectImages} />
        {/if}
        <div class="inner">
            <slot></slot>
        </div>
    </div>

</main>
<style>
    main {
        border: dashed 2px var(--color-three);
        border-radius: 25px;
        padding: 10px;
    }
    :global(main iframe) {
        border: dashed 2px var(--color-three);
        border-radius: 20px;
        padding: 10px;
        margin-left: auto;
    }
    .outer {
        display: grid;
        grid-template-columns: 1fr 2fr;
        gap: 10px;
    }
    .inner {
        display: flex;
        justify-content: space-between;
        flex-direction: column;
        font-size: 1.5rem;
    }
</style>