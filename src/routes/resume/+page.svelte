<script lang="ts">
    import HeaderCard from "$lib/HeaderCard.svelte";
    import Article from "$lib/Article.svelte";
    import Link from "$lib/Link.svelte";
</script>
<svelte:head>
    <title>Resume</title>
</svelte:head>
<main>
    <HeaderCard>My Resume</HeaderCard>
    <embed src="/resume.pdf" type="application/pdf" />
</main>
<style>
    main {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
    embed {
        width: 906px;
        max-width: 100%;
        height: 100%;
        border-radius: 30px;
        border: 2px dashed var(--tan);
        padding: 10px;
    }
</style>