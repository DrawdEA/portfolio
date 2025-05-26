<script>
    import { gsap } from "gsap";
    import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';
	import { onMount } from 'svelte';
	gsap.registerPlugin(ScrollTrigger);

    import cardgame from "$lib/images/projects/cardgame.png";
    const { projectName = "Unknown Project", image = cardgame, tools = ["Tool 1", "Tool 2", "Tool 3", "Tool 4"] } = $props();

    onMount(() => {
        gsap.from(`#${projectName.replaceAll(" ", "")}`, {
            scrollTrigger: {
                trigger: `#${projectName.replaceAll(" ", "")}`,
                toggleActions: "play none none none",
                start: "-105% 90%",
                end: "20% 90%",
                scrub: 1,
                once: true
            },
            y: "100%",
            duration: 0.5,
            opacity: 0
        })
    })
</script>

<div 
    class="flex flex-col items-center mb-4 justify-between rounded-4xl w-auto object-cover h-70 mx-5" id={projectName.replaceAll(" ", "")} 
    style="background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.4)), url({image}); background-size: cover; background-position: center"
>
    <h1 class="pt-5 text-2xl md:text-3xl xl:text-4xl text-center">{projectName}</h1>
    <div class="flex  flex-col sm:flex-row gap-2 md:gap-10 pb-3 text-xs md:text-base">
        {#each tools as tool}
        <p class="text-center">{tool}</p>
        {/each}
    </div>
</div>