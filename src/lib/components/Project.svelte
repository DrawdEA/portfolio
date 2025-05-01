<script>
    import cardgame from "$lib/images/projects/cardgame.png";
    const { projectName = "Unknown Project", image = cardgame, tools = ["Tool 1", "Tool 2", "Tool 3", "Tool 4"] } = $props();
</script>

<div 
    class="flex flex-col items-center mb-12 justify-between rounded-4xl w-300 h-75" 
    style="background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.4)), url({image}); background-size: cover; background-position: center"
>
    <h1 class="pt-5 text-4xl">{projectName}</h1>
    <div class="flex gap-10 pb-3 text-base">
        {#each tools as tool}
        <p>{tool}</p>
        {/each}
    </div>
</div>