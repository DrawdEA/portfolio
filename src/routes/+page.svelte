<script>
    import { Project, TechTool } from "$lib/index.js";
    import selfPortrait from "$lib/images/portraits/chloe.jpg";
</script>

<div class="text-3xl flex flex-col gap-100 mt-50 items-center">
    <div class="flex gap-20 justify-center items-center">
        <div class="flex flex-col">
            <p class="text-8xl">Hello,</p>
            <p class="text-6xl pb-3">I'm Edward Diesta.</p>
            <p class="text-3xl">
                <span class="bg-red-800">A Software Engineer.</span>
            </p>
        </div>
        <div>
            <img src={selfPortrait} alt="Self Protrait" class="h-75 w-75 object-fit rounded-full">
        </div>
    </div>

    <div class="flex flex-col items-center">
        <p class="pb-15 text-5xl">Here are some of the things I'm working on.</p>
        <Project />
        <Project />
        <Project />
    </div>

    <div class="flex flex-col items-center">
        <p class="pb-15 text-5xl">
            These are what I use to <span class="bg-red-800">create</span>.
        </p>
        <div class="grid grid-cols-5 grid-rows-5 gap-10">
            <TechTool toolName="SvelteKit" />
            <TechTool toolName="Svelte" />
            <TechTool toolName="TailwindCSS"/>
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


