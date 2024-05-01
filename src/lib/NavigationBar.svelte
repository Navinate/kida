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

    export let visible = false;
</script>
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
<style>
    nav {
        color: var(--canary);
        border-radius: 30px;
        border-color: var(--canary);
        border-width: 2px;
        border-style: dashed;
        display: flex;
        flex-direction: column;
        gap: 15px;
        min-width: 250px;
        max-width: 300px;
        overflow: scroll;
        padding: 10px;
        transition-duration: 1s;
        transform-origin: top right;
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
        border-radius: 15px;
        outline: 2px dashed var(--canary);
        outline-offset: -10px;
        padding: 15px;
        font-size: 2rem;
        transition-duration: 1s;
        backdrop-filter: blur(5px);
    }
    @media (max-width: 768px) {
        nav {
            position: absolute;
            top: 5px;
            right: 5px;
            margin: 0px;
            z-index: 100;
            background-image: url('/icons/loader.svg');
            background-color: var(--chambray);
            padding: 10px;
            opacity: 1;
        }
        ul {
            gap: 40px;
            padding: 20px 5px;
            border-radius: 15px;
        }
        li {
            outline-offset: -5px;
            padding: 10px;
            font-size: 2rem;
            transition-duration: 1s;
        }
    }
</style>
{#if !visible}
    <style>
        nav {
            transform: translateX(150%) rotate(-45deg);
        }
    </style>
{/if}