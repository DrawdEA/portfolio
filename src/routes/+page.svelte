<script>
    import { Project, TechTool } from "$lib/index.js";
    import selfPortrait from "$lib/images/portraits/edward.jpg";

    // Logo Images
    import bootstrap from "$lib/images/logos/bootstrap.png";
    import git from "$lib/images/logos/git.png";
    import github from "$lib/images/logos/github.png";
    import java from "$lib/images/logos/java.png";
    import javascript from "$lib/images/logos/javascript.png";
    import nextjs from "$lib/images/logos/nextjs.png";
    import python from "$lib/images/logos/python.png";
    import react from "$lib/images/logos/react.png";
    import sqlite from "$lib/images/logos/sqlite.png";
    import tailwind from "$lib/images/logos/tailwind.png";
    import svelte from "$lib/images/logos/svelte.png";
    import tensorflow from "$lib/images/logos/tensorflow.png";
    import zustand from "$lib/images/logos/zustand.png";
    import django from "$lib/images/logos/django.svg";
    import numpy from "$lib/images/logos/numpy.svg";
    import vercel from "$lib/images/logos/vercel.svg";

    // Project Images
    import cardgame from "$lib/images/projects/cardgame.png";
    import cs50finance from "$lib/images/projects/cs50finance.png";
    import dormvouch from "$lib/images/projects/dormvouch.png";
    import guessmyprompt from "$lib/images/projects/guessmyprompt.png";
    import todolist from "$lib/images/projects/todolist.png";
    import weatherapp from "$lib/images/projects/weatherapp.png";
    import zengarden from "$lib/images/projects/zengarden.png";

    // Import animation
    import { gsap } from "gsap";
    import { ScrollTrigger } from 'gsap/ScrollTrigger';
    import { SplitText } from "gsap/SplitText";
	import { onMount } from 'svelte';
	

    onMount(() => {
        gsap.registerPlugin(ScrollTrigger, SplitText);

        // Hero texts.
        let tl = gsap.timeline();

        let heroSplit = SplitText.create("#edward", {
            type: "words"
        })

        let softwareSplit = SplitText.create("#role", {
            type: "words"
        })

        tl
        .from("#hello", {
            duration: 0.5,
            y: "100%",
            opacity: 0,
            yoyo: true
        })
        .from(heroSplit.words, {
            opacity: 0,
            duration: 1,
            y: "100%",
            stagger: 0.1
        }, "+=0.1")
        .from("#portrait", {
            opacity: 0,
            duration: 0.5,
        }, "+=0.1")
        .from(softwareSplit.words, {
            opacity: 0,
            y: "100%",
            duration: 1,
            stagger: 0.1
        }, "+=0.1")
        .fromTo("#software", {
            backgroundColor: "#000000",
        }, {
            backgroundColor: "#1c398e",
            duration: 0.5,
        })

        // First text.
        let split = SplitText.create(".animatedText", {
            type: "words"
        })

        let texttl = gsap.timeline({scrollTrigger: {
            trigger: split.words,
            toggleActions: "restart none none none",
            start: "top 100%",
            end: "bottom 100%",
        }});

        texttl.from(split.words, {
            y: "200%",
            autoAlpha: 0,
            stagger: 0.1,
            opacity: 0
        }).fromTo("#engineer", {
            backgroundColor: "#000000",
        }, {
            backgroundColor: "#1c398e",
            duration: 0.3,
        })

        // Second text.
        let split2 = SplitText.create(".animatedText2", {
            type: "words"
        })

        let texttl2 = gsap.timeline({scrollTrigger: {
            trigger: split2.words,
            toggleActions: "restart resume resume resume",
            start: "top 100%",
            end: "bottom 100%",
        }});

        texttl2.from(split2.words, {
            y: "200%",
            autoAlpha: 0,
            stagger: 0.1,
            opacity: 0
        }).fromTo("#create", {
            backgroundColor: "#000000",
        }, {
            backgroundColor: "#1c398e",
            duration: 0.3,
        })

        // Tools.
        gsap.from(".tool", {
            scrollTrigger: {
                trigger: ".tool",
                toggleActions: "restart pause resume pause",
                start: "-100% 100%",
                end: "200% 100%",
                scrub: 1
            },
            ease: "power1.out",
            y: "200%",
            duration: 0.5,
            stagger: 0.05
        })
    })
</script>

<div class="text-3xl flex flex-col gap-100 mt-50 items-center">
    <div class="flex max-md:flex-col gap-20 justify-center items-center">
        <div class="flex flex-col max-md:items-center">
            <p class="text-5xl sm:text-6xl md:text-7xl xl:text-8xl" id="hello">Hello,</p>
            <p class="text-3xl sm:text-4xl md:text-5xl xl:text-6xl pb-3" id="edward">I'm Edward Diesta.</p>
            <p class="text-lg sm:text-xl md:text-2xl xl:text-3xl" id="role">A <span class="bg-blue-900" id="software">Software Engineer</span>.</p>
        </div>
        <div>
            <img src={selfPortrait} alt="Self Protrait" class="h-55 w-55 md:h-60 md:w-60 xl:h-75 xl:w-75 object-fit rounded-full" id="portrait">
        </div>
    </div>

    <div class="flex flex-col items-auto object-cover">
        <p class="pb-15 text-center text-3xl md:text-4xl xl:text-5xl break-normal mx-5 animatedText">Here are some of the things <span class="bg-blue-900" id="engineer">I'm working on</span>.</p>
        <Project projectName="Weather App" image={weatherapp} tools={["JavaScript", "HTML", "CSS", "Weather Crossing API"]} />
        <Project projectName="Guess My Prompt" image={guessmyprompt} tools={["Next.JS", "Zustand", "TailwindCSS", "DeepSeek R1 API"]} />
        <Project projectName="To-Do List" image={todolist} tools={["JavaScript", "HTML", "CSS"]} />
        <Project projectName="DormVouch" image={dormvouch} tools={["JavaScript", "HTML", "CSS"]} />
        <Project projectName="Ateneo Zen Garden Scenery Game" image={zengarden} tools={["Java", "Swing"]} />
        <Project projectName="Finance Stocks Simulator" image={cs50finance} tools={["Flask", "JavaScript", "HTML", "CSS"]} />
        <Project projectName="RPG Card Game" image={cardgame} tools={["Java", "Swing"]} />
    </div>

    <div class="flex flex-col items-center">
        <p class="pb-15 text-center text-3xl md:text-4xl xl:text-5xl break-normal mx-5 animatedText2">
            These are what I use to <span class="bg-blue-900" id="create">create</span>.
        </p>
        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 xl:grid-cols-6 gap-5 items-stretch justify-stretch mb-50">
            <TechTool toolName="Next.JS" image={nextjs} />
            <TechTool toolName="Svelte" image={svelte} />
            <TechTool toolName="TailwindCSS" image={tailwind} />
            <TechTool toolName="React" image={react} />
            <TechTool toolName="Zustand" image={zustand} />
            <TechTool toolName="Java" image={java} />
            <TechTool toolName="Python" image={python} />
            <TechTool toolName="Vercel" image={vercel} />
            <TechTool toolName="SvelteKit" image={svelte} />
            <TechTool toolName="JavaScript" image={javascript} />
            <TechTool toolName="Git" image={git} />
            <TechTool toolName="GitHub" image={github} />
            <TechTool toolName="SQLite" image={sqlite} />
            <TechTool toolName="Bootstrap" image={bootstrap} />
            <TechTool toolName="TensorFlow" image={tensorflow} />
            <TechTool toolName="NumPy" image={numpy} />
            <TechTool toolName="Django" image={django} />
        </div>
    </div>
</div>


