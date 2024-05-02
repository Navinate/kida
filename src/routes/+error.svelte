<script>
    // @ts-nocheck
    import { page } from '$app/stores';
</script>
<svelte:head>
    <title>Error</title>
</svelte:head>
<main>
    <div>
        <h1>{$page.status}:</h1>
        <h2>{$page.error.message}</h2>
    </div>
</main>

<style>
  main {
    height: 100vh;
    width: 100%;
    font-size: 3rem;
    display: grid;
    place-items: center;
  }
  div {
    display: flex;
    flex-direction: column;
  }
</style>
