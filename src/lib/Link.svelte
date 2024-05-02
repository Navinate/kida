<script>
    export let href = '';
    export let block = false;
    export let size = 2;
</script>
{#if block}
<div>
    <a href={href} style="font-size: {size}rem">
        <slot/>
    </a>
</div>
{:else}
    <a href={href} style="font-size: {size}rem">
        <slot/>
    </a>
{/if}
<style>
    a {
        cursor: pointer;
        color: var(--color-four);
    }
</style>