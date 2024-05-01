<script>
    export let title = "Title";
    export let image = "https://via.placeholder.com/150";
    export let link = "https://www.google.com";
</script>
<a href={link}>
    <main>  
        <img src={image} alt={title} />
        <h1>{title}</h1>
    </main>
</a>
<style>
    main {
        max-width: 100%;
        aspect-ratio: 1/1;
        font-size: 4rem;
        color: var(--canary);
        border-radius: 15px;
        border-color: var(--canary);
        border-width: 1px;
        border-style: dashed;
        display: grid;
        grid-template-rows: 1fr 2fr;
        padding: 10px;
        position: relative;
    }

    img {
        width: 100%;
        height: 100%;
        object-fit: cover;
        border-radius: 10px;
    }

    h1 {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        font-size: 2rem;
    }

    a {
        text-decoration: none;
    }
</style>