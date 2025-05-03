<script>
    import svelte from "$lib/images/logos/svelte.png";
    let { toolName = "Tool Name", image = svelte } = $props();
</script>

<div class="flex flex-col justify-center items-center h-40 w-40 bg-[#252525] rounded-4xl gap-4 tool">
    
    <img src={image} alt="Logo" class="object-contain h-20 w-20">
    <p class="text-xl">{toolName}</p>
</div>