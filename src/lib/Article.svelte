<script>
    export let projectTitle;
    export let projectImages;
</script>
<main>
<h1>{projectTitle}</h1>
<div>
    {#if projectImages}
        <img src={projectImages[0]} alt={projectTitle} />
    {:else}
        <div></div>
    {/if}
</div>
</main>
<style>

</style>