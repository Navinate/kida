<script>
	import HeaderCard from "$lib/HeaderCard.svelte";
    import Highlight from "$lib/Highlight.svelte";

</script>
<main>
    <HeaderCard>Writings</HeaderCard>
<Highlight projectTitle="StairWELL" anchor="/thesis" fullText="/writing/thesis">
    My masters thesis on interaction design for large scale interactive art.
</Highlight>
</main>
<style>
    main {
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
</style>