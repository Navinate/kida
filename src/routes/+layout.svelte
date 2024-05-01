<script lang="ts">
    import { onMount } from 'svelte';
    onMount(() => {
        let listElements = document.querySelectorAll('li');
        for(let li of listElements){
            if(Math.random() > 0.5){
                li.dataset.direction = 'left';
                li.style.transform = 'rotate(-10deg)';
                li.style.textAlign = 'start';
            } else {
                li.dataset.direction = 'right';
                li.style.transform = 'rotate(10deg)';
                li.style.textAlign = 'end';
            }
            li.addEventListener('mouseenter', () => {
                if(li.dataset.direction === 'left'){
                    li.dataset.direction = 'right';
                    li.style.transform = 'rotate(10deg)';
                    li.style.textAlign = 'end';
                } else {
                    li.dataset.direction = 'left';
                    li.style.transform = 'rotate(-10deg)';
                    li.style.textAlign = 'start';
                }
            });
        }
    });
</script>

<div id="container">
    <nav>
        <h1>Trey Cluff</h1>
        <ul>
            <a href="/"><li>About</li></a>
            <a href="/thesis"><li>Thesis</li></a>
            <a href="/web"><li>Websites</li></a>
            <a href="/games"><li>Games</li></a>
            <a href="/art"><li>Art</li></a>
            <a href="/contact"><li>Contact</li></a>
        </ul>
    </nav>
    <main>
        <slot></slot>
    </main>
</div>
<style>
    #container{
        width: 100vw;
        height: 100vh;
        display: flex;
        flex-direction: row;
        max-width: 1200px;
        margin: 0px auto;
        gap: 10px;
        padding: 5px;
    }
    nav, main {
        color: var(--canary);
        border-radius: 20px;
        border-color: var(--canary);
        border-width: 1px;
        border-style: dashed;
    }
    main {
        width: 80%;
        display: grid;
        place-items: center;
        overflow: scroll;
        padding: 10px;
    }
    nav {
        display: flex;
        flex-direction: column;
        gap: 15px;
        min-width: 10%;
        overflow: scroll;
        padding: 10px;
    }
    h1{
        font-size: 3rem;
    }
    ul{
        list-style-type: none;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        gap: 50px;
        width: 100%;
        min-height: 100%;

    }
    a {
        text-decoration: none; 
        color: var(--canary);
    }
    li {
        transform-origin: center;
        background-color: rgba(0, 0, 0, 0.3);
        border-radius: 10px;
        outline: 1px solid var(--canary);
        outline-offset: -10px;
        padding: 15px;
        font-size: 2rem;
        transition-duration: 1s;
    }

</style>