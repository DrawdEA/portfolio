<script>
    import { Project, TechTool } from "$lib/index.js";
    import selfPortrait from "$lib/images/chloe.jpg";
</script>

<div class="text-3xl flex flex-col gap-30 mt-30 items-center">
    <div class="flex gap-20 justify-center items-center">
        <div class="flex flex-col">
            <p class="text-5xl">Hello.</p>
            <p class="text-4xl">I am Edward Diesta.</p>
            <p class="text-xl">A Software Engineer.</p>
        </div>
        <div>
            <img src={selfPortrait} alt="Self Protrait" class="h-60 w-60 object-fit rounded-full">
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
            <TechTool toolName="SvelteKit" />
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


