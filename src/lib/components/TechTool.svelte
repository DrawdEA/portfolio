<script>
    import svelte from "$lib/images/logos/svelte.png";
    let { toolName = "Tool Name", image = svelte } = $props();
</script>

<div class="flex flex-col justify-center items-center h-52 w-52 bg-[#252525] rounded-4xl gap-4">
    
    <img src={image} alt="Logo" class="object-contain h-30 w-30">
    <p class="text-2xl">{toolName}</p>
</div>