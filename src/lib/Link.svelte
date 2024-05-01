<script>
    export let href = '';
    export let block = false;
</script>
{#if block}
<div>
    <a href={href}>
        <slot/>
    </a>
</div>
{:else}
    <a href={href}>
        <slot/>
    </a>
{/if}
<style>
    a {
        cursor: pointer;
        font-size: 2rem;
        color: var(--light-tan);
    }
</style>