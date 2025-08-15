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
    export let mobile = false;
    function hideMenu(){
        if(mobile) {
            visible = false;
        }
    }
</script>
<nav>
    <br>
    <ul>
        <a href="/" on:click={hideMenu}>                <li class="readable-background">Home</li></a>
        <a href="/blog/thesis" on:click={hideMenu}>     <li class="readable-background">Thesis</li></a>
        <a href="/web" on:click={hideMenu}>             <li class="readable-background">Web Apps</li></a>
        <a href="/games" on:click={hideMenu}>           <li class="readable-background">Games</li></a>
        <a href="/art" on:click={hideMenu}>             <li class="readable-background">Art</li></a>
        <a href="/blog" on:click={hideMenu}>            <li class="readable-background">Blog</li></a>
        <a href="/contact" on:click={hideMenu}>         <li class="readable-background">Contact</li></a>
        <a href="/resume" on:click={hideMenu}>          <li class="readable-background smol">Resumé</li></a>
    </ul>
</nav>
<style>
    nav {
        color: var(--color-four);
        display: flex;
        flex-direction: column;
        gap: 20px;
        min-width: 250px;
        max-width: 350px;
        overflow: auto;
        padding: 10px;
        transition-duration: 1s;
        transform-origin: top right;
    }
    ul{
        list-style-type: none;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        gap: 50px;
        width: 100%;
        min-height: 90%;
    }
    a {
        color: var(--color-four);
        font-size: 2rem;
    }
    li {
        transform-origin: center;
        border-width: var(--border-width, 0px);
        border-radius: var(--radius, 0px);
        padding: 10px;
        transition-duration: 1.5s; 
    }
    .smol {
        font-size: 1.25rem;
    }
    @media (max-width: 768px) {
        nav {
            position: absolute;
            top: 5px;
            right: 5px;
            margin: 0px;
            z-index: 100;
            background-image: url('/icons/loader.svg');
            background-color: var(--color-one);
            padding: 10px;
            max-width: 250px;
        }
        ul {
            padding: 20px 5px;
            border-radius: var(--radius, 15px);;
        }
        li {
            outline-offset: -5px;
            padding: 10px;
            font-size: 2rem;
        }
    }
</style>
{#if !visible}
    <style>
        nav {
            transform: translateX(150%);
        }
    </style>
{/if}