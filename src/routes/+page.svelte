<script>
    import Project from "$lib/Project.svelte";
    import TechTool from "$lib/TechTool.svelte";
</script>

<div class="flex flex-col gap-30 mt-30 items-center">
    <div class="flex">
        <div class="flex flex-col">
            <p class="font-tommy">Hello.</p>
            <p>I am Edward Diesta.</p>
            <p>A Software Engineer.</p>
        </div>
        <div>
            <img src="a" alt="placeholder">
        </div>
    </div>

    <div class="flex flex-col items-center">
        <p class="pb-5">Here are some of the things I'm working on.</p>
        <Project />
        <Project />
        <Project />
    </div>

    <div class="flex flex-col items-center pb-30">
        <p class="pb-5">These are what I use to create. innovate. reimagine. execute.</p>
        <div class="grid grid-cols-5 grid-rows-5 gap-2">
            <TechTool />
            <TechTool />
            <TechTool />
            <TechTool />
            <TechTool />
            <TechTool />
            <TechTool />
            <TechTool />
            <TechTool />
            <TechTool />
        </div>
    </div>
</div>


