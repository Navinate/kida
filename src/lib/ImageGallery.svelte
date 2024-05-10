<script lang="ts">
export let images: string[] = [];
let currentIndex = 0;
function updateImage(direction: number) {
    return () => {
        currentIndex = (currentIndex + direction + images.length) % images.length;
    };
}
</script>
<div id="image-container">
    {#if images.length > 1}
        <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
        <img src="icons/left-arrow.svg" class="navigation-arrow left" alt="Previous" on:click={updateImage(-1)} on:keypress={updateImage(-1)}/>
        {#each images as image, i}
            <!-- svelte-ignore a11y-missing-attribute -->
            <img class="subject-image" src={image} style="opacity: {i === currentIndex ? 1 : 0.0};" />
        {/each}
        <!-- svelte-ignore a11y-no-noninteractive-element-interactions -->
        <img src="icons/right-arrow.svg" class="navigation-arrow right" alt="Next" on:click={updateImage(1)} on:keypress={updateImage(1)} />
    {:else}
        <!-- svelte-ignore a11y-missing-attribute -->
        <img class="subject-image" src={images[0]} />
    {/if}
</div>
<style>
    #image-container {
        width: 400px;
        aspect-ratio: 1/1;
        padding: 10px;
        position: relative;
        border-radius: var(--radius, 20px);;
        border-width: 2px;
    }

    .navigation-arrow {
        position: absolute;
        cursor: pointer;
        top: 50%;
        transform: translateY(-50%);
        z-index: 1;
        transition-duration: 0.2s;
    }
    .navigation-arrow:hover {
        filter: invert(1);
    }
    .left {
        left: 20px;
    }
    .right {
        right: 20px;
    }

    .subject-image {
        position: absolute;
        width: calc(100% - 20px);
        aspect-ratio: 1/1;
        transition-duration: 0.5s;
        border-radius: var(--radius, 15px);;
    }
    @media (max-width: 768px) {
        #image-container {
            max-width: 300px;
        }
    }
</style>