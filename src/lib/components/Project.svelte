<script>
    let { projectName = "Unknown Project", fileName = "todolist.png", tools = ["Tool 1", "Tool 2", "Tool 3", "Tool 4"] } = $props();
</script>

<div 
class="flex flex-col items-center mb-12 justify-between bg-[linear-gradient(rgba(0,0,0,0.4),rgba(0,0,0,0.4)),url('$lib/images/projects/todolist.png')] bg-center bg-cover rounded-4xl w-300 h-50">
    <h1 class="pt-5 text-4xl">{projectName}</h1>
    <div class="flex gap-10 pb-3 text-base">
        {#each tools as tool}
        <p>{tool}</p>
        {/each}
    </div>
</div>