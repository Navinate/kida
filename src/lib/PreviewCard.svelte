<script lang="ts">
    export let image = "https://via.placeholder.com/150";
    export let link = "/";
</script>
<a href={link}>
    <main class="readable-background">  
        <img src={image} alt="preview of project" />
        <h1><slot></slot></h1>
    </main>
</a>
<style>
    main {
        border-radius: var(--radius, 25px);;
        border-width: 2px;
        padding: 10px;
        position: relative;
        display: grid;
        place-items: center;
    }

    a img {
        border-radius: var(--radius, 20px);;
        object-fit: cover;
        aspect-ratio: 1/1;
        width: 100%;
        transition-duration: 0.2s; 
    }
    a:hover img {
        filter: brightness(0.2);
        
    }

    a h1 {
        color: var(--color-four);
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        font-size: 2rem;
        opacity: 0;
        transition-duration: 0.2s;
    }
    a:hover h1 {
        opacity: 1; 
    }
</style>