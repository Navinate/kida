<script lang="ts">
    import HeaderCard from "$lib/HeaderCard.svelte";
</script>
<svelte:head>
    <title>Trey Cluff - Resumé</title>
</svelte:head>
<main>
    <HeaderCard>My Resumé</HeaderCard>
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
        border: 2px dashed var(--color-three);
        padding: 10px;
    }
</style>