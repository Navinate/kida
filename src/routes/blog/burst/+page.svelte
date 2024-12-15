<script lang="ts">
    import Article from "$lib/Article.svelte";
    import HeaderCard from "$lib/HeaderCard.svelte";
    import Link from "$lib/Link.svelte";
</script>
<svelte:head>
    <title>BURST</title>
</svelte:head>
<main>
    <HeaderCard>BURST</HeaderCard>
    <Article>
        <Link href="https://burst.purduehackers.com" size={1.5}>BURST website</Link>
        I attended (and helped put on) the Purdue Hackers 2024 BURST exhibition.  I am a former member of the club and travelled back to Purdue to help execute and attend the event.  None of the work below is mine, just my favorite exhibits by my friends.
        <div class="outer">
            <div class="inner">
                <img src="/burst/title.jpg" alt="Burst logo" />
                <subtitle>The show's introduction signage</subtitle>
            </div>
            <div class="inner">
                <img src="/burst/sign.jpg" alt="LED sign of an abstract H" />
                <subtitle>The club's logo constructed into an LED sign (mostly designed by Jack)</subtitle>
            </div>
        </div>
        <div class="outer">
            <div class="inner">
                <img src="/burst/passports.jpg" alt="Club members' passports displayed on a wall" />
                <subtitle>The club makes custom passports</subtitle>
            </div>
            <div class="inner">
                <img src="/burst/badges.jpg" alt="Every badge displayed in a chronological spiral" />
                <subtitle>The club hands out custom badges at every Hack Night event</subtitle>
            </div>
        </div>
        <div class="outer">
            <div class="inner">
                <img src="/burst/printer.jpg" alt="Custom receipt printer printing messages from a Discord channel" />
                <subtitle>A receipt printer that prints messages from a Discord channel</subtitle>
            </div>
            <div class="inner">
                <img src="/burst/vines.jpg" alt="wall decals displaying secret messages encoded in a plant alphabet" />
                <subtitle>Secret messages encoded in "VineScript", a custom plant based alphabet</subtitle>
            </div>
        </div>
    </Article>
</main>
<style>
    main {
        width: 100%;
        height: 100%;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
    subtitle {
        font-size: 1rem;
    }

    .outer {
        display: grid;
        gap: 10px;
        grid-template-columns: 1fr 1fr;
    }
    .inner {
        display: flex;
        flex-direction: column;
        gap: 10px;
    }

    img {
        object-fit: cover;
        overflow: hidden;
        object-position: center;
    }

    @media only screen and (max-width: 600px) {
        .outer {
            grid-template-columns: 1fr;
        }
    }
</style>