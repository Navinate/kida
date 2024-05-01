<script lang="ts">
    import NavigationBar from '$lib/NavigationBar.svelte';
    import { onMount } from 'svelte';

    $: windowWidth = 0;
    $: isMenuVisible = true;
    onMount(() => {
        window.addEventListener('resize', () => {
            windowWidth = window.innerWidth;
        });
    
    });
    function toggleMenuVisibility(){
        isMenuVisible = !isMenuVisible;
    }
</script>

<div id="container">
    <NavigationBar visible={isMenuVisible}></NavigationBar>
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
        max-width: 1000px;
        margin: 0px auto;
        gap: 10px;
        padding: 5px;
    }
    main {
        color: var(--canary);
        border-radius: 30px;
        border-color: var(--canary);
        border-width: 2px;
        border-style: dashed;
        display: grid;
        place-items: center;
        overflow: scroll;
        padding: 10px;
    }

    #menu-button {
        width: 50px;
        height: 50px;
        padding: 10px;
        place-self: start;
        border: 2px dashed var(--canary);
        border-radius: 15px;
        margin-bottom: 10px;
        cursor: pointer;
    }
    #menu-button:active {
        background-color: var(--canary);
        border-color: var(--chambray);
    }
    #menu-button img {
        width: 100%;
        height: 100%;
    }
</style>