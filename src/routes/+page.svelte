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
        <Project projectName="Guess-My-Prompt Web Game" fileName="guessmyprompt.png" tools={["Next.JS", "Zustand", "TailwindCSS", "DeepSeek R1 API"]} />
        <Project projectName="Weather App" fileName="weatherapp.png" tools={["JavaScript", "HTML", "CSS", "Weather Crossing API"]} />
        <Project projectName="To-Do List" fileName="todolist.png" tools={["JavaScript", "HTML", "CSS"]} />
        <Project projectName="DormVouch" fileName="dormvouch.png" tools={["JavaScript", "HTML", "CSS"]} />
        <Project projectName="Ateneo Zen Garden Scenery Game" fileName="zengarden.png" tools={["Java", "Swing"]} />
        <Project projectName="C$50 Finance Stocks Simulator" fileName="cs50finance.png" tools={["Flask", "JavaScript", "HTML", "CSS"]} />
        <Project projectName="RPG-Esque Card Game" fileName="cardgame.png" tools={["Java", "Swing"]} />
    </div>

    <div class="flex flex-col items-center">
        <p class="pb-15 text-5xl">
            These are what I use to <span class="bg-red-800">create</span>.
        </p>
        <div class="grid grid-cols-5 grid-rows-5 gap-10">
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


