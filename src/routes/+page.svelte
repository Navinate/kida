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
    <title>Home</title>
</svelte:head>
<main>
    <HeaderCard>Hello,</HeaderCard>
    <!-- svelte-ignore a11y-no-static-element-interactions -->
    <p>I am {article} <span>{randomTitle}</span><br>who loves to solve creative problems with technology.</p>
    <p>This website documents most of my work including my masters thesis, abstract art, and video games.</p>
    <subtitle>Below are some highlights :)</subtitle>
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
    #article-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
        gap: 10px;
    }
    p {
        font-size: 1.5rem;
    }
    span {
        text-decoration: underline;
        font-size: 2rem;
    }
    subtitle {
        font-size: 1.5rem;
    }
</style>