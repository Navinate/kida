<script lang="ts">
    export let image = "https://via.placeholder.com/150";
    export let link = "/";
</script>
<a href={link}>
    <main>  
        <img src={image} alt="preview of project" />
        <h1><slot></slot></h1>
    </main>
</a>
<style>
    main {
        border-radius: 25px;
        border: dashed 2px var(--tan);
        padding: 10px;
        position: relative;
        backdrop-filter: blur(5px);
        display: grid;
        place-items: center;
    }

    a img {
        border-radius: 20px;
        width: 100%;
        transition-duration: 0.2s; 
    }
    a:hover img {
        filter: brightness(0.2);
        
    }

    a h1 {
        color: var(--light-tan);
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