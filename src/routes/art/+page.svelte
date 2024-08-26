<script lang="ts">
    import Highlight from "$lib/Highlight.svelte";
import HeaderCard from "$lib/HeaderCard.svelte";
</script>
<svelte:head>
    <title>Trey Cluff - Art</title>
</svelte:head>
<main>
    <HeaderCard>My Art</HeaderCard>
    <Highlight projectTitle="Fractal Series" anchor="fractal" projectImages={["/art/fractal_1.jpg", "/art/fractal_2.jpg", "/art/fractal_3.jpg"]}>
        I have always been fascinated by fractals and their infinite construction. Here are some of my works using chaos games to generate fractals in Processing.  Showcased at the 2023 FRACTAL Purdue CGT Student Showcase (name was a coincidence) and the 2024 FRC Indiana Championship Tech Art Expo.
    </Highlight>
    <Highlight projectTitle="Lenticular Confetti" anchor="confetti" projectImages={["/art/confetti_1.jpg", "/art/confetti_2.jpg", "/art/confetti_3.jpg", "/art/confetti_4.jpg"]}>
        Lenticular Confetti is a series of works that explore concentric circles and tranlucent layers to create fun, abstract, shapes that float on their own.  Made with Processing
    </Highlight>
    <Highlight projectTitle="Drips" anchor="drips" projectImages={["/art/drips_1.png", "/art/drips_2.png", "/art/drips_3.png", "/art/drips_4.png", "/art/drips_5.png"]}>
        Made with Processing, Drips is a series of sketches exploring randomness defined by order.  Each sketch is uniquie in color and shape.
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