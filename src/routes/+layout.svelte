<script lang="ts">
    import NavigationBar from '$lib/NavigationBar.svelte';
    import { onMount } from 'svelte';

    export let radius: number = 0;

    $: windowWidth = 1000;
    $: mobile = windowWidth < 768;
    $: isMenuVisible = !mobile;
    onMount(() => {
        windowWidth = window.innerWidth;
        window.addEventListener('resize', () => {
            windowWidth = window.innerWidth;
            if(!mobile && !isMenuVisible) toggleMenuVisibility();
        });
    
    });
    function toggleMenuVisibility(){
        isMenuVisible = !isMenuVisible;
    }
</script>

<div id="container">
    <NavigationBar visible={isMenuVisible} {mobile}></NavigationBar>
    <main>
        {#if windowWidth < 768}
            <!-- svelte-ignore a11y-click-events-have-key-events -->
            <!-- svelte-ignore a11y-no-static-element-interactions -->
            <div id="menu-button" on:click={toggleMenuVisibility} class="readable-background">
                <img src="/icons/menu.svg" alt="menu" />
            </div>
        {/if}
        <slot radius="{radius}px"></slot> 
    </main>
    
</div>
<style>
    #container{
        width: 100vw;
        height: 100vh;
        display: grid;
        grid-template-columns: 1fr 4fr;
        max-width: 1200px;
        margin: 0px auto;
        gap: 10px;
        padding: 5px;
    }
    main {
        color: var(--color-four);
        border-width: var(--border-width, 0px);
        border-radius: var(--radius, 0px);
        overflow-y: scroll;
        padding: 10px;
        display: grid;
    }

    #menu-button {
        width: 50px;
        height: 50px;
        padding: 10px;
        place-self: start;
        border-width: var(--border-width, 0px);
        border-radius: var(--radius, 0px);
        margin-bottom: 10px;
        cursor: pointer;
    }
    
    #menu-button:active {
        background-color: var(--color-four);
        border-color: var(--color-one);
    }
    #menu-button img {
        width: 100%;
        height: 100%;
    }
    @media (max-width: 768px) {
        #container {
            grid-template-columns: 1fr;
        }
    }
</style>