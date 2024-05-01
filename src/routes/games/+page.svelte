<script lang="ts">
    import HeaderCard from "$lib/HeaderCard.svelte";
    import Article from "$lib/Article.svelte";
    import Link from "$lib/Link.svelte";
</script>
<svelte:head>
    <title>Games</title>
</svelte:head>
<main>
    <HeaderCard>My Games</HeaderCard>
    <Article projectTitle="COMING SOON">
        This page is currently under construction.  In the meantime, check out my games on <Link href="https://navinate.itch.io">Itch.io</Link>
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