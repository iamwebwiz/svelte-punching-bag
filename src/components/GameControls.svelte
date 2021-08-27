<script>
    export let gameEnded;
    export let punchBag;
    export let resetGame;
</script>

<div class="flex justify-center gap-2 mt-10 items-center">
    {#if !gameEnded}
        <button on:click={punchBag} class="px-5 py-2 bg-blue-800 hover:bg-blue-900 text-blue-100 rounded border-0">
            Punch
        </button>
    {/if}
    <button on:click={resetGame} class="px-5 py-2 bg-red-800 hover:bg-red-900 text-red-100 rounded border-0">
        Reset
    </button>
</div>
