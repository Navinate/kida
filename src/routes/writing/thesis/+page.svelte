<script lang="ts">
    import Article from "$lib/Article.svelte";
    import HeaderCard from "$lib/HeaderCard.svelte";
    import Link from "$lib/Link.svelte";
</script>
<svelte:head>
    <title>Trey Cluff - Thesis</title>
</svelte:head>
<main>
    <HeaderCard>My Masters Thesis</HeaderCard>
    <Article>
        <Link href="https://github.com/Purdue-Stairwell" size={1.5}>The StairWELL Github</Link>
        <img src="/thesis/night.jpg" alt="StairWELL sculpture at night" />
        <subtitle>The sculpture at night</subtitle>
        <p>
            The StairWELL sculpture was a large scale interdisiplinary project completed in Fall 2023.
            I was the lead designer and programmer for the interactivity system for the sculpture.
            I developed a web application for users to interact with the sculpture in Svelte.
            The back end for managing the data was built using web sockets and a Redis database.
            I wrote my thesis about the interaction system for my Master's of Science.
            Here is the abstract from the thesis itself:
        </p>
            <blockquote>
                This research project aims to create an interactivity system for an interactive art exhibit named StairWELL. The StairWELL project is a sculpture that focuses on the emotional wellness of students through art. The interactive technology design is broken down into three components: a mobile device interface, a data processing server, and sculpture visualization. Each of these components has been defined to help the larger StairWELL team achieve its artistic goals. The goal of this paper is to show that mobile devices can be used as an effective participation method for interactive art installations. It also aims to show how an interactive art piece can accept data from many users in rapid succession.
            </blockquote>
        <p>
            I worked on this project for the better of 2 years straight.
            I worked with Purdue's Convocations department and other university stakeholders to brainstorm and prototype an interactive art sculpture to raise awareness about student mental health.
        </p>
        <p>The full thesis is available at
            <Link href="https://hammer.purdue.edu/articles/thesis/IMPROVING_INTERACTIVE_ART_EXPERIENCES_WITH_MOBILE_DEVICE_INTERACTION/24749463" size={1.5}>Purdue Hammer</Link>
        </p>
        <!-- svelte-ignore a11y-media-has-caption -->
        <video autoplay controls muted>
            <source src="/thesis/day.mp4" type="video/mp4" />
            Your browser does not support the video tag.
        </video>
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
</style>