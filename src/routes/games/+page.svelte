<script lang="ts">
    import HeaderCard from "$lib/HeaderCard.svelte";
	import Game from "$lib/Game.svelte";
</script>
<svelte:head>
    <title>Trey Cluff - Games</title>
</svelte:head>
<main>
    <HeaderCard>My Games</HeaderCard>
    <Game projectTitle="Elder Angler" projectImages={["games/elder_angler1.png","games/elder_angler2.png","games/elder_angler3.png","games/elder_angler4.png","games/elder_angler5.png"]}>
        <p>I made this game in 5 days for the Fish Fest Game jam.  I had a lot of fun designing the main character and the enviromental hazards.  The game was made using Blender and Godot.  I tried to recreate a more retro PSX style graphics</p>
        <iframe title="Elder Angler" frameborder="0" src="https://itch.io/embed/2628186?dark=true" width="208" height="167"><a href="https://navinate.itch.io/elder-angler">Elder Angler by Navinate</a></iframe>
    </Game>
    <Game projectTitle="Rhubarb Garden" projectImages={["games/rhubarb1.png"]}>
        <p>I made this game over 2 weeks for the Acerola Game jam 0.  This was my first solid attempt at making a game and my first game jam.  I am not proud of the quality of the game but I am proud of the amount of learning I achieved while creating the game.  This game was made in Godot using custom Blender make assets and Kenney assets (CC0)</p>
        <iframe title="Rhubarb Garden" frameborder="0" src="https://itch.io/embed/2580632?dark=true" width="208" height="167"><a href="https://navinate.itch.io/rhubarb-garden">Rhubarb Garden by Navinate</a></iframe>
    </Game>
    <br>
</main>
<style>
    main {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
</style>