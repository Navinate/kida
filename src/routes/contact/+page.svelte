<script lang="ts">
    import Highlight from "$lib/Highlight.svelte";
    import HeaderCard from "$lib/HeaderCard.svelte";
    import Link from "$lib/Link.svelte";
</script>
<svelte:head>
    <title>Trey Cluff - Contact</title>
</svelte:head>
<main>
    <HeaderCard>Contact Me!</HeaderCard>
    <Highlight projectTitle="Work In Progress" anchor="email">
        This page is currently under construction.  In the meantime, feel free to reach out to me on <Link href="https://www.linkedin.com/in/thomas-cluff/" block>LinkedIn</Link> or <Link href="https://twitter.com/treysnoise" block>Twitter</Link>
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