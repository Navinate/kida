<script lang="ts">
    import { onMount } from 'svelte';
	import PreviewCard from "$lib/PreviewCard.svelte";
    import HeaderCard from "$lib/HeaderCard.svelte";

    let titles = ["Creative Coder", "Computational Artist", "Web Developer"];

    $: randomTitle = titles[Math.floor(Math.random() * titles.length)];
    $: article = "AEIOU".includes(randomTitle.charAt(0)) ? "an" : "a";

    function newTitle() {
        randomTitle = titles[Math.floor(Math.random() * titles.length)];
        article = "AEIOU".includes(randomTitle.charAt(0)) ? "an" : "a";
    }

    onMount(() => {
        const timer = setInterval(newTitle, 3000);

        return () => {
            clearInterval(timer);
        };
    });

</script>
<svelte:head>
    <title>Trey Cluff</title>
    <meta name="description" content="Trey Cluff's personal website.">
    <meta name="keywords" content="Trey Cluff, Trey, Cluff, personal website, portfolio, creative technologist, immersive developer, creative coder, computational artist, interactivity specialist">
    <meta name="author" content="Trey Cluff">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="robots" content="index, follow">
</svelte:head>
<main>
    <HeaderCard>Hello, I'm Trey</HeaderCard>
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div id="intro-text" class="readable-background">
        <p>I am {article} <span>{randomTitle}</span><br>and a graduate of Purdue University. I have experience in developing front-end applications using Svelte, TypeScript, and Processing, as well as creating immersive experiences using Unity and Godot.</p>
        <br>
        <p>This website documents some of my work including my masters thesis, abstract art, and video games.</p>
        <br>
        <p>Below are some highlights :)</p>
    </div>
    <div id="article-grid">
        <PreviewCard image="/thesis/night.jpg" link="/blog/thesis">Masters Thesis</PreviewCard>
        <PreviewCard image="/art/fractal_1.jpg" link="/art">Fractal Art</PreviewCard>
        <PreviewCard image="games/elder_angler1.png" link="/games#ea">Elder Angler</PreviewCard>
        <PreviewCard image="/web/ac_1.jpg" link="/web#ac">Art Guessing Game</PreviewCard>
        <PreviewCard image="/burst/title.jpg" link="/blog/burst">Burst Show</PreviewCard>
    </div>
    <br>
</main>

<style>
    main {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        gap: 10px;
    }
    
    #intro-text {
        border-width: var(--border-width, 0px);
        border-radius: var(--radius, 0px);
        padding: 10px;
    }
    #article-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
        gap: 10px;
    }

    @media only screen and (max-width: 600px) {
        #article-grid {
            grid-template-columns: 1fr 1fr;
        }
    }
</style>