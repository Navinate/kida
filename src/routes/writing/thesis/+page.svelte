<script lang="ts">
    import HeaderCard from "$lib/HeaderCard.svelte";
    import Highlight from "$lib/Highlight.svelte";
    import Link from "$lib/Link.svelte";
</script>
<svelte:head>
    <title>Trey Cluff - Thesis</title>
</svelte:head>
<main>
    <HeaderCard>My Masters Thesis</HeaderCard>
    <Highlight projectTitle="COMING SOON">
        This page is currently under construction.  In the meantime, check out my thesis <Link href="https://convocations.purdue.edu/stairwell/">here</Link>
    </Highlight>
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