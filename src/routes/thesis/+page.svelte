<script lang="ts">
    import HeaderCard from "$lib/HeaderCard.svelte";
    import Article from "$lib/Article.svelte";
    import Link from "$lib/Link.svelte";
</script>
<svelte:head>
    <title>Thesis</title>
</svelte:head>
<main>
    <HeaderCard>My Masters Thesis</HeaderCard>
    <Article projectTitle="COMING SOON">
        This page is currently under construction.  In the meantime, check out my thesis <Link href="https://convocations.purdue.edu/stairwell/">here</Link>
    </Article>
</main>
<style>
    main {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
</style>