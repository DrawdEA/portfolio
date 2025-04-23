<script>
    import imageSource from "$lib/images/logos/svelte.png";
    let { toolName = "Tool Name" } = $props();
</script>

<div class="flex flex-col justify-center items-center h-52 w-52 bg-[#252525] rounded-4xl gap-4">
    <img src={imageSource} alt="Logo" class="object-cover h-30">
    <p class="text-2xl">{toolName}</p>
</div>