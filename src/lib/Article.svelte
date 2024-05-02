<article class="readable-background">
    <slot></slot>
</article>
<style>
    article {
        width: 100%;
        height: fit-content;
        color: var(--color-four);
        border-radius: 25px;
        border: dashed 2px var(--color-three);
        padding: 10px;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 10px;
    }
    :global(article p) {
        font-size: 1rem;
        line-height: 2rem;
        padding: 0px 10px;
    }
    :global(article img) {
        height: 400px;
        border-radius: 20px;
        border: dashed 2px var(--color-three);
        padding: 10px;
    }
    :global(article subtitle) {
        font-size: 1.5rem;
        color: var(--color-three);
    }
    :global(article blockquote) {
        font-size: 1rem;
        line-height: 2rem;
        padding: 0px 10px;
        border: dashed 2px var(--color-three);
        border-radius: 15px;
        margin-left: 30px;
    }
    :global(article video) {
        width: 100%;
        height: 400px;
        border-radius: 20px;
        border: dashed 2px var(--color-three);
        padding: 10px;
    }
</style>