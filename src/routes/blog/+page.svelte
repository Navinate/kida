<script>
	import HeaderCard from "$lib/HeaderCard.svelte";
    import Highlight from "$lib/Highlight.svelte";

</script>
<main>
    <HeaderCard>My Web Log</HeaderCard>
<Highlight projectTitle="StairWELL" anchor="/thesis" fullText="/blog/thesis">
    My masters thesis on interaction design for large scale interactive art.
</Highlight>
<Highlight projectTitle="BURST" anchor="/burst" fullText="/blog/burst">
    Some highlights from the Purdue Hackers 2024 BURST exhibition.
</Highlight>
</main>
<style>
    main {
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
</style>