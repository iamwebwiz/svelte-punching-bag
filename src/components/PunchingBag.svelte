<script>
    export let gameEnded;
</script>

<main class="flex justify-center">
    {#if (!gameEnded)}
        <img src="/healthy-bag.png" alt="healthy bag">
    {:else}
        <img src="/destroyed-bag.png" alt="destroyed bag">
    {/if}
</main>
