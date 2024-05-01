<script lang="ts">
    import { onMount } from 'svelte';
	import ArticleCard from "$lib/ArticleCard.svelte";
    import HeaderCard from "$lib/HeaderCard.svelte";

    let titles = ["Creative Technologist", "Immersive Developer", "Creative Coder", "Computational Artist", "Interactivity Specialist"];

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
    <HeaderCard>Hello,</HeaderCard>
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <div id="intro-text">
        <p>I am {article} <span>{randomTitle}</span><br>who loves to solve creative problems with technology.</p>
        <p>This website documents most of my work including my masters thesis, abstract art, and video games.</p>
        <p>Below are some highlights :)</p>
    </div>
    <div id="article-grid">
        <ArticleCard image="https://via.placeholder.com/200" link="/thesis">Masters Thesis</ArticleCard>
        <ArticleCard image="/art/fractal_1.jpg" link="/art">Fractal Art</ArticleCard>
        <ArticleCard image="https://via.placeholder.com/200" link="/games">Elder Angler</ArticleCard>
        <ArticleCard image="/web/ac_1.jpg" link="/web#ac">Art Guessing Game</ArticleCard>
    </div>
</main>

<style>
    main {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        gap: 20px;
    }
    
    #intro-text {
        border: dashed 2px var(--color-three);
        border-radius: 20px;
        padding: 10px;
        backdrop-filter: blur(7px);
    }
    p {
        font-size: 1.5rem;
    }
    span {
        text-decoration: underline;
        font-size: 2rem;
    }
    #article-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
        gap: 10px;
    }
</style>