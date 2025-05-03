<script>
    import { gsap } from "gsap";
    import { ScrollTrigger } from 'gsap/ScrollTrigger';
	import { onMount } from 'svelte';
	gsap.registerPlugin(ScrollTrigger);

    import cardgame from "$lib/images/projects/cardgame.png";
    const { projectName = "Unknown Project", image = cardgame, tools = ["Tool 1", "Tool 2", "Tool 3", "Tool 4"] } = $props();

    onMount(() => {
        gsap.from(`#${projectName.replaceAll(" ", "")}`, {
            scrollTrigger: {
                trigger: `#${projectName.replaceAll(" ", "")}`,
                toggleActions: "restart pause resume pause",
                start: "-105% 90%",
                end: "20% 90%",
                scrub: 1
            },
            ease: "power1.in",
            y: "100%",
            duration: 0.5,
            width: 300
        })
    })


</script>

<div 
    class="flex flex-col items-center mb-12 justify-between rounded-4xl w-300 h-75" id={projectName.replaceAll(" ", "")} 
    style="background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.4)), url({image}); background-size: cover; background-position: center"
>
    <h1 class="pt-5 text-4xl">{projectName}</h1>
    <div class="flex gap-10 pb-3 text-base">
        {#each tools as tool}
        <p>{tool}</p>
        {/each}
    </div>
</div>