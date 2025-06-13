<script>
  import { onMount } from "svelte";

  const {
    projectName = "Unknown Project",
    image = "/path/to/default.png",
    tools = ["Tool 1", "Tool 2"],
    link = "https://github.com",
  } = $props();

  const elementId = projectName.replaceAll(" ", "");

  onMount(async () => {
    const { gsap } = await import("gsap");
    const { ScrollTrigger } = await import("gsap/dist/ScrollTrigger");

    gsap.registerPlugin(ScrollTrigger);

    // Scroll-in Animation (unchanged)
    gsap.from(`#${elementId}`, {
      scrollTrigger: {
        trigger: `#${elementId}`,
        toggleActions: "play none none none",
        start: "top bottom",
        once: true,
      },
      y: 100,
      duration: 0.5,
      opacity: 0,
    });

    // --- UPDATED: Hover Animation Timeline ---
    const hoverTimeline = gsap.timeline({ paused: true });

    hoverTimeline.to(`#${elementId}`, {
      scale: 1.05,
      duration: 0.2,
      ease: "power2.out",
    });

    const wrapper = document.querySelector(`#wrapper-${elementId}`);

    if (wrapper) {
      wrapper.addEventListener("mouseenter", () => hoverTimeline.play());
      wrapper.addEventListener("mouseleave", () => hoverTimeline.reverse());
    }
  });
</script>

<a
  id="wrapper-{elementId}"
  href={link}
  target="_blank"
  rel="noopener noreferrer"
  class="block"
>
  <div
    id={elementId}
    class="flex flex-col items-center mb-4 justify-between rounded-4xl w-auto object-cover h-70 mx-5"
    style="background: linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.2), rgba(0, 0, 0, 0.4)), url({image}); background-size: cover; background-position: center"
  >
    <h1 class="pt-5 text-2xl md:text-3xl xl:text-4xl text-center">
      {projectName}
    </h1>
    <div
      class="flex flex-col sm:flex-row gap-2 md:gap-10 pb-3 text-xs md:text-base"
    >
      {#each tools as tool}
        <p class="text-center">{tool}</p>
      {/each}
    </div>
  </div>
</a>