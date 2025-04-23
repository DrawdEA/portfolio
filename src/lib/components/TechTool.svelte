<script>
    import imageSource from "$lib/images/chloe.jpg";
    let { toolName = "Tool Name" } = $props();
    
</script>

<div class="flex flex-col justify-center items-center h-60 w-60 bg-amber-950 rounded-lg gap-4">
    <img src={imageSource} alt="Logo" class="rounded-full h-30 w-30">
    <p>{toolName}</p>
</div>