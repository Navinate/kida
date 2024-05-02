<script lang="ts">
    import Highlight from "$lib/Highlight.svelte";
    import HeaderCard from "$lib/HeaderCard.svelte";
    import Link from "$lib/Link.svelte";
</script>
<svelte:head>
    <title>Trey Cluff - Websites</title>
</svelte:head>
<main>
    <HeaderCard>My Web Projects</HeaderCard>
    <Highlight projectTitle="Stratagem ➡️ Emojis" anchor="s2e" projectImages={["/web/s2e_2.jpg","/web/s2e_1.jpg"]}>
        Small web app I made to quickly convert WASD / Arrow key inputs into emojis. It also features a quiz mode to test your stratagem memorization. Inspired by the amazing game Helldivers 2.
        <Link href="https://stratagem-emoji.vercel.app/" block={true}>Link</Link>
    </Highlight>
    <Highlight projectTitle="Albers' Challenge" anchor="ac" projectImages={["/web/ac_1.jpg"]}>
        A fun little game I made while @ Purdue Hackers hack night. The goal is to guess the presented color even though it is being contrasted by random colors. The design is inspired by fun and Josef Albers' work.
        <Link href="https://albers.navinate.com" block={true}>Link</Link>
    </Highlight>
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