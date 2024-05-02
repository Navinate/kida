<div class="readable-background"><slot></slot></div>
<style>
    div {
        width: 100%;
        height: fit-content;
        font-size: 5rem;
        color: var(--color-four);
        border-radius: 20px;
        border: dashed 2px var(--color-three);
        padding: 5px 10px;
        display: grid;
        place-items: center start;
    }
    @media (max-width: 900px) {
        div {
            font-size: 3rem;
            padding: 2.5px 5px;
        }
    }
</style>