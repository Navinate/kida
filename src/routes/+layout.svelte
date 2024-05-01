<script lang="ts">
    import NavigationBar from '$lib/NavigationBar.svelte';
    import { onMount } from 'svelte';

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
            <div id="menu-button" on:click={toggleMenuVisibility}>
                <img src="/icons/menu.svg" alt="menu" />
            </div>
        {/if}
        <slot></slot>
    </main>
</div>
<style>
    #container{
        width: 100vw;
        height: 100vh;
        display: flex;
        flex-direction: row;
        justify-content: center;
        max-width: 1200px;
        margin: 0px auto;
        gap: 10px;
        padding: 5px;
    }
    main {
        color: var(--color-four);
        border-radius: 30px;
        border-color: var(--color-three);
        border-width: 2px;
        border-style: dashed;
        overflow-y: scroll;
        padding: 10px;
    }

    #menu-button {
        width: 50px;
        height: 50px;
        padding: 10px;
        place-self: start;
        border: 2px dashed var(--color-three);
        border-radius: 15px;
        margin-bottom: 10px;
        cursor: pointer;
        backdrop-filter: blur(5px);
    }
    
    #menu-button:active {
        background-color: var(--color-four);
        border-color: var(--color-one);
    }
    #menu-button img {
        width: 100%;
        height: 100%;
    }
</style>