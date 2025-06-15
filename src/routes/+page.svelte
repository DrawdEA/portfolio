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

    // About Me Images
    import imsummit1 from "$lib/images/aboutme/imsummit1.jpg";
    import imsummit2 from "$lib/images/aboutme/imsummit2.jpg";
    import ateneo from "$lib/images/aboutme/ateneo.png";
    import compsat from "$lib/images/aboutme/compsat.png";
    import cs50 from "$lib/images/aboutme/cs50.png";
    import deeplearning from "$lib/images/aboutme/deeplearning.png";
    import odin from "$lib/images/aboutme/odin.png";
    import gym from "$lib/images/aboutme/gym.jpg";
    import basketball from "$lib/images/aboutme/basketball.jpg";
    import roblox from "$lib/images/aboutme/roblox.jpg";
    import arrow from "$lib/images/aboutme/ChevronDoubleUp.svg";

    // Import animation
    import { gsap } from "gsap";
    import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';
    import { SplitText } from "gsap/SplitText";
	import { onMount } from 'svelte';

    onMount(() => {
        gsap.registerPlugin(ScrollTrigger, SplitText);

        window.onload = () => {
            ScrollTrigger.refresh();
        };

        // Hero texts.
        let tl = gsap.timeline();

        let heroSplit = SplitText.create("#edward", {
            type: "words"
        })

        let softwareSplit = SplitText.create("#role", {
            type: "words"
        })

       tl.to(".maindiv", {
        duration: 0,
        opacity: 1,
        })
        .from("#hello", {
            duration: 0.4,
            y: "100%",
            opacity: 0,
        })
        .from(
            heroSplit.words,
            {
            opacity: 0,
            duration: 0.7,
            y: "100%",
            stagger: 0.04,
            },
            "<+0.1",
        )
        .from(
            softwareSplit.words,
            {
            opacity: 0,
            y: "100%",
            duration: 0.7,
            stagger: 0.04,
            },
            "<+0.2",
        )
        .fromTo(
            "#software",
            {
            backgroundColor: "#121212",
            },
            {
            backgroundColor: "#1c398e",
            duration: 0.4,
            },
            "<+0.4",
        )
        .from(
            "#portrait",
            {
            opacity: 0,
            duration: 0.6,
            },
            "<+0.1",
        )
        .from(
            ".social-icon",
            {
            opacity: 0, // Start invisible
            y: 20, // Start slightly lower
            duration: 0.5, // How long each icon takes to animate
            stagger: 0.1, // The magic property: 0.1s delay between each icon
            },
            "<+0.1", // Start this sequence 0.5s after the text animation begins
        );

        // First text.
        let split = SplitText.create(".animatedText", {
            type: "words"
        })

        let texttl = gsap.timeline({scrollTrigger: {
            trigger: split.words,
            toggleActions: "play none none none",
            start: "top 100%",
            end: "bottom 100%",
        }});

        texttl.from(split.words, {
            y: "200%",
            autoAlpha: 0,
            stagger: 0.03,
            opacity: 0
        })

        // Second text.
        let split2 = SplitText.create(".animatedText2", {
            type: "words"
        })

        let texttl2 = gsap.timeline({scrollTrigger: {
            trigger: split2.words,
            toggleActions: "play none none none",
            start: "top 100%",
            end: "bottom 100%",
        }});

        texttl2.from(split2.words, {
            y: "200%",
            autoAlpha: 0,
            stagger: 0.03,
            opacity: 0
        })

        // Tools.
        let tools = gsap.utils.toArray(".tool");

        gsap.from(".tool", {
        scrollTrigger: {
            trigger: "#tech-stack", // Trigger when the whole section comes into view
            toggleActions: "play none none none",
            start: "top 75%", // Start when the top of the section is 75% down the viewport
            once: true,
        },
        y: 40,
        opacity: 0,
        duration: 0.4,
        stagger: 0.05, // This will now work correctly, animating each tool in sequence.
        });

        tools.forEach((tool) => {
        const hoverTimeline = gsap.timeline({ paused: true });

        hoverTimeline.to(tool, {
            scale: 1.1, // A bit bigger for smaller icons
            duration: 0.2,
            ease: "power2.out",
        });

        tool.addEventListener("mouseenter", () => hoverTimeline.play());
        tool.addEventListener("mouseleave", () => hoverTimeline.reverse());
        });

        // About me.
        let sections = gsap.utils.toArray(".section");

        sections.forEach((section) => {
            gsap.from(section, {
                scrollTrigger: {
                    trigger: section,
                    toggleActions: "play none none none",
                    start: "top-=100% 100%",
                    end: "top-=50% 100%",
                    scrub: 1,
                    once: true
                },
                y: "100%",
                duration: 0.5,
                opacity: 0
            })
        })
    })

    // The email address to be copied
    let email = "edwardjoshua.diesta@gmail.com";

    // Reactive state variables
    let copied = false;
    let tooltipText = "Copy email";

    // This function handles the click event
    const copyEmail = async () => {
        // Prevent running again if already in "copied" state
        if (copied) return;

        try {
        await navigator.clipboard.writeText(email);

        // --- Success State ---
        copied = true;
        tooltipText = "Copied!";

        // Reset the state after 2 seconds
        setTimeout(() => {
            copied = false;
            tooltipText = "Copy email";
        }, 2000);
        } catch (err) {
        // --- Error State ---
        console.error("Failed to copy email: ", err);
        tooltipText = "Copy failed!";

        // Reset the tooltip text after 2 seconds
        setTimeout(() => {
            tooltipText = "Copy email";
        }, 2000);
        }
    };
</script>

<main class="text-3xl flex flex-col gap-25 ">
    <section class="flex max-md:flex-col gap-10 md:gap-20 justify-center items-center max-md:-translate-y-[3rem] opacity-0 h-[calc(100vh_-_6rem)] maindiv">
        <div class="flex flex-col max-md:items-center">
            <p class="text-5xl sm:text-6xl md:text-7xl xl:text-8xl" id="hello">Hello,</p>
            <p class="text-3xl sm:text-4xl md:text-5xl xl:text-6xl md:pb-2" id="edward">I'm Edward Diesta.</p>
            <p class="text-lg sm:text-xl md:text-2xl xl:text-3xl" id="role">A <span class="bg-blue-900" id="software">Full-Stack Developer</span>.</p>
            
            <nav aria-label="Social media links" class="pt-5 text-gray-400">
                <ul class="flex items-center gap-5">
                    <!-- GitHub Link -->
                    <li class="social-icon">
                    <a
                        href="https://github.com/DrawdEA"
                        target="_blank"
                        rel="noopener noreferrer"
                        aria-label="GitHub"
                        class="transition-colors hover:text-white"
                    >
                        <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="36px"
                        height="36px"
                        viewBox="0 0 32 32"
                        fill="currentColor"
                        >
                        <path
                            fill-rule="evenodd"
                            d="M 16 4 C 9.371094 4 4 9.371094 4 16 C 4 21.300781 7.4375 25.800781 12.207031 27.386719 C 12.808594 27.496094 13.027344 27.128906 13.027344 26.808594 C 13.027344 26.523438 13.015625 25.769531 13.011719 24.769531 C 9.671875 25.492188 8.96875 23.160156 8.96875 23.160156 C 8.421875 21.773438 7.636719 21.402344 7.636719 21.402344 C 6.546875 20.660156 7.71875 20.675781 7.71875 20.675781 C 8.921875 20.761719 9.554688 21.910156 9.554688 21.910156 C 10.625 23.746094 12.363281 23.214844 13.046875 22.910156 C 13.15625 22.132813 13.46875 21.605469 13.808594 21.304688 C 11.144531 21.003906 8.34375 19.972656 8.34375 15.375 C 8.34375 14.0625 8.8125 12.992188 9.578125 12.152344 C 9.457031 11.851563 9.042969 10.628906 9.695313 8.976563 C 9.695313 8.976563 10.703125 8.65625 12.996094 10.207031 C 13.953125 9.941406 14.980469 9.808594 16 9.804688 C 17.019531 9.808594 18.046875 9.941406 19.003906 10.207031 C 21.296875 8.65625 22.300781 8.976563 22.300781 8.976563 C 22.957031 10.628906 22.546875 11.851563 22.421875 12.152344 C 23.191406 12.992188 23.652344 14.0625 23.652344 15.375 C 23.652344 19.984375 20.847656 20.996094 18.175781 21.296875 C 18.605469 21.664063 18.988281 22.398438 18.988281 23.515625 C 18.988281 25.121094 18.976563 26.414063 18.976563 26.808594 C 18.976563 27.128906 19.191406 27.503906 19.800781 27.386719 C 24.566406 25.796875 28 21.300781 28 16 C 28 9.371094 22.628906 4 16 4 Z"
                        ></path>
                        </svg>
                    </a>
                    </li>
                    <!-- Facebook Link -->
                    <li class="social-icon">
                    <a
                        href="https://www.facebook.com/edwardjoshua.diesta/"
                        target="_blank"
                        rel="noopener noreferrer"
                        aria-label="Facebook"
                        class="transition-colors hover:text-white"
                    >
                        <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="36px"
                        height="36px"
                        viewBox="0 0 32 32"
                        fill="currentColor"
                        >
                        <path
                            d="M 16 4 C 9.3844276 4 4 9.3844276 4 16 C 4 22.615572 9.3844276 28 16 28 C 22.615572 28 28 22.615572 28 16 C 28 9.3844276 22.615572 4 16 4 z M 16 6 C 21.534692 6 26 10.465308 26 16 C 26 21.027386 22.311682 25.161277 17.488281 25.878906 L 17.488281 18.916016 L 20.335938 18.916016 L 20.783203 16.023438 L 17.488281 16.023438 L 17.488281 14.443359 C 17.488281 13.242359 17.882859 12.175781 19.005859 12.175781 L 20.810547 12.175781 L 20.810547 9.6523438 C 20.493547 9.6093438 19.822688 9.515625 18.554688 9.515625 C 15.906688 9.515625 14.355469 10.913609 14.355469 14.099609 L 14.355469 16.023438 L 11.632812 16.023438 L 11.632812 18.916016 L 14.355469 18.916016 L 14.355469 25.853516 C 9.6088556 25.070647 6 20.973047 6 16 C 6 10.465308 10.465308 6 16 6 z"
                        ></path>
                        </svg>
                    </a>
                    </li>
                    <!-- Instagram Link -->
                    <li class="social-icon">
                    <a
                        href="https://www.instagram.com/d_rawde/"
                        target="_blank"
                        rel="noopener noreferrer"
                        aria-label="Instagram"
                        class="transition-colors hover:text-white"
                    >
                        <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="36px"
                        height="36px"
                        viewBox="0 0 32 32"
                        fill="currentColor"
                        >
                        <path
                            d="M 11.46875 5 C 7.917969 5 5 7.914063 5 11.46875 L 5 20.53125 C 5 24.082031 7.914063 27 11.46875 27 L 20.53125 27 C 24.082031 27 27 24.085938 27 20.53125 L 27 11.46875 C 27 7.917969 24.085938 5 20.53125 5 Z M 11.46875 7 L 20.53125 7 C 23.003906 7 25 8.996094 25 11.46875 L 25 20.53125 C 25 23.003906 23.003906 25 20.53125 25 L 11.46875 25 C 8.996094 25 7 23.003906 7 20.53125 L 7 11.46875 C 7 8.996094 8.996094 7 11.46875 7 Z M 21.90625 9.1875 C 21.402344 9.1875 21 9.589844 21 10.09375 C 21 10.597656 21.402344 11 21.90625 11 C 22.410156 11 22.8125 10.597656 22.8125 10.09375 C 22.8125 9.589844 22.410156 9.1875 21.90625 9.1875 Z M 16 10 C 12.699219 10 10 12.699219 10 16 C 10 19.300781 12.699219 22 16 22 C 19.300781 22 22 19.300781 22 16 C 22 12.699219 19.300781 10 16 10 Z M 16 12 C 18.222656 12 20 13.777344 20 16 C 20 18.222656 18.222656 20 16 20 C 13.777344 20 12 18.222656 12 16 C 12 13.777344 13.777344 12 16 12 Z"
                        ></path>
                        </svg>
                    </a>
                    </li>
                    <!-- LinkedIn Link -->
                    <li class="social-icon">
                    <a
                        href="https://www.linkedin.com/in/edward-joshua-diesta-263132233/"
                        target="_blank"
                        rel="noopener noreferrer"
                        aria-label="LinkedIn"
                        class="transition-colors hover:text-white"
                    >
                        <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="36px"
                        height="36px"
                        viewBox="0 0 32 32"
                        fill="currentColor"
                        >
                        <path
                            d="M 7.5 5 C 6.132813 5 5 6.132813 5 7.5 L 5 24.5 C 5 25.867188 6.132813 27 7.5 27 L 24.5 27 C 25.867188 27 27 25.867188 27 24.5 L 27 7.5 C 27 6.132813 25.867188 5 24.5 5 Z M 7.5 7 L 24.5 7 C 24.785156 7 25 7.214844 25 7.5 L 25 24.5 C 25 24.785156 24.785156 25 24.5 25 L 7.5 25 C 7.214844 25 7 24.785156 7 24.5 L 7 7.5 C 7 7.214844 7.214844 7 7.5 7 Z M 10.4375 8.71875 C 9.488281 8.71875 8.71875 9.488281 8.71875 10.4375 C 8.71875 11.386719 9.488281 12.15625 10.4375 12.15625 C 11.386719 12.15625 12.15625 11.386719 12.15625 10.4375 C 12.15625 9.488281 11.386719 8.71875 10.4375 8.71875 Z M 19.46875 13.28125 C 18.035156 13.28125 17.082031 14.066406 16.6875 14.8125 L 16.625 14.8125 L 16.625 13.5 L 13.8125 13.5 L 13.8125 23 L 16.75 23 L 16.75 18.3125 C 16.75 17.074219 16.996094 15.875 18.53125 15.875 C 20.042969 15.875 20.0625 17.273438 20.0625 18.375 L 20.0625 23 L 23 23 L 23 17.78125 C 23 15.226563 22.457031 13.28125 19.46875 13.28125 Z M 9 13.5 L 9 23 L 11.96875 23 L 11.96875 13.5 Z"
                        ></path>
                        </svg>
                    </a>
                    </li>

                    <!-- Email Copy Button -->
                    <li class="flex items-center pl-2 social-icon">
                    <!-- The `relative` class is removed, and `flex items-center` is added -->
                    <button
                        on:click={copyEmail}
                        aria-label="Copy email address"
                        class="group transition-colors hover:text-white"
                    >
                        {#if copied}
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="28px"
                            height="28px"
                            viewBox="0 -960 960 960"
                            fill="currentColor"
                            
                        >
                            <path d="M382-240 154-468l57-57 171 171 367-367 57 57z" />
                        </svg>
                        {:else}
                        <!-- Default Icon: Mail -->
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="28px"
                            height="28px"
                            viewBox="0 -960 960 960"
                            fill="currentColor"
                            class="block group-hover:hidden"
                        >
                            <path
                            d="M160-160q-33 0-56.5-23.5T80-240v-480q0-33 23.5-56.5T160-800h640q33 0 56.5 23.5T880-720v480q0 33-23.5 56.5T800-160zm320-280L160-640v400h640v-400zm0-80 320-200H160zM160-640v-80 480z"
                            />
                        </svg>
                        <!-- Hover Icon: Copy -->
                        <svg
                            xmlns="http://www.w3.org/2000/svg"
                            width="28px"
                            height="28px"
                            viewBox="0 -960 960 960"
                            fill="currentColor"
                            class="hidden group-hover:block"
                        >
                            <path
                            d="M360-240q-33 0-56.5-23.5T280-320v-480q0-33 23.5-56.5T360-880h360q33 0 56.5 23.5T800-800v480q0 33-23.5 56.5T720-240zm0-80h360v-480H360zM200-80q-33 0-56.5-23.5T120-160v-560h80v560h440v80zm160-240v-480z"
                            />
                        </svg>
                        {/if}
                    </button>
                    </li>

                    <!-- Portfolio / Resume Link -->
                    <li class="pl-2 social-icon">
                    <a
                        href="/resume.pdf"
                        download="EdwardDiesta_Resume.pdf"
                        aria-label="Download Portfolio"
                        class="group transition-colors hover:text-white"
                    >
                        <!-- Default Icon: Portfolio -->
                        <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="28px"
                        height="28px"
                        viewBox="0 -960 960 960"
                        fill="currentColor"
                        class="block group-hover:hidden"
                        >
                        <path
                            d="M480-240q-56 0-107 17.5T280-170v10h400v-10q-42-35-93-52.5T480-240m0-80q69 0 129 21t111 59v-560H240v560q51-38 111-59t129-21m0-160q-25 0-42.5-17.5T420-540t17.5-42.5T480-600t42.5 17.5T540-540t-17.5 42.5T480-480M240-80q-33 0-56.5-23.5T160-160v-640q0-33 23.5-56.5T240-880h480q33 0 56.5 23.5T800-800v640q0 33-23.5 56.5T720-80zm240-320q58 0 99-41t41-99-41-99-99-41-99 41-41 99 41 99 99 41m0-140"
                        />
                        </svg>
                        <!-- Hover Icon: Download -->
                        <svg
                        xmlns="http://www.w3.org/2000/svg"
                        width="28px"
                        height="28px"
                        viewBox="0 -960 960 960"
                        fill="currentColor"
                        class="hidden group-hover:block"
                        >
                        <path
                            d="M480-320 280-520l56-58 104 104v-326h80v326l104-104 56 58zM240-160q-33 0-56.5-23.5T160-240v-120h80v120h480v-120h80v120q0 33-23.5 56.5T720-160z"
                        />
                        </svg>
                    </a>
                    </li>
                </ul>
            </nav>
        </div>
        <div>
            <img src={selfPortrait} alt="Edward Joshua Diesta's portrait" class="h-55 w-55 md:h-60 md:w-60 xl:h-75 xl:w-75 object-fit rounded-full" id="portrait">
        </div>
        

        
    </section>

    <section class="flex flex-col items-auto object-cover scroll-mt-25" id="projects">
        <p class="pb-15 text-center text-3xl md:text-4xl xl:text-5xl break-normal mx-5 animatedText">Here are some of the things I'm working on.</p>
        <Project link="https://drawdea.github.io/weather-app/" projectName="Weather App" image={weatherapp} tools={["JavaScript", "HTML", "CSS", "Weather Crossing API"]} />
        <Project link="https://guess-my-prompt-six.vercel.app/" projectName="Guess My Prompt" image={guessmyprompt} tools={["Next.JS", "Zustand", "TailwindCSS", "DeepSeek R1 API"]} />
        <Project link="https://drawdea.github.io/to-do-list/" projectName="To-Do List" image={todolist} tools={["JavaScript", "HTML", "CSS"]} />
        <Project link="https://www.youtube.com/watch?v=IOjknlBMk3E" projectName="DormVouch" image={dormvouch} tools={["JavaScript", "HTML", "CSS"]} />
        <Project link="https://github.com/DrawdEA/ateneo-zen-garden" projectName="Ateneo Zen Garden Scenery Game" image={zengarden} tools={["Java", "Swing"]} />
        <Project projectName="Finance Stocks Simulator" image={cs50finance} tools={["Flask", "JavaScript", "HTML", "CSS"]} />
        <Project link="https://github.com/DrawdEA/card-game" projectName="RPG Card Game" image={cardgame} tools={["Java", "Swing"]} />
    </section>

    <section class="flex flex-col items-center scroll-mt-25" id="tech-stack">
        <p class="pb-15 text-center text-3xl md:text-4xl xl:text-5xl break-normal mx-5 animatedText2">
            These are what I use to create.
        </p>
        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 xl:grid-cols-6 gap-4 items-stretch justify-stretch">
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
    </section>

    <section class="flex flex-col items-center bg-background w-full pb-20 rounded-[4rem] scroll-mt-25" id="about">
        <div class="flex flex-col items-center w-9/10 mx-10 gap-4">
            <img src={arrow} alt="Arrow" class="w-auto h-20 rounded-4xl object-cover mb-10">
            
            <div class="flex flex-col items-center h-auto w-full bg-main rounded-4xl rounded-t-[4rem] gap-4 section p-10">
                <p class="pb-4 text-center text-2xl md:text-3xl xl:text-4xl break-normal mx-5">
                    About Me    
                </p>
                <p class="text-sm md:text-base xl:text-lg">
                    As an <span class="bg-blue-900">avid problem solver</span>, I am always on the lookout to learn new things. 
                    What helps me keep motivated is that I seek to <span class="bg-blue-900">create things that can help 
                    other people in various nifty ways</span>, which is usually how I plan out my future 
                    projects!
                </p>
            </div>

            <div class="flex flex-col lg:flex-row w-full gap-4">
                <div class="flex flex-col items-center h-auto w-full lg:w-2/5 bg-main rounded-4xl gap-4 section p-10">
                    <p class="text-2xl md:text-3xl xl:text-4xl text-center">From Roblox?</p>
                    <p class="text-sm md:text-base xl:text-lg">
                        The first time I was actually exposed to programming <span class="bg-blue-900">was back when I was in Grade 5:</span>
                        Trying to make a quick buck, I learned the scripting language LUA through youtube tutorials 
                        over the summer break. With these, I made simple elemental battle games, and a pong clone from scratch.
                    </p>
                    <img src={roblox} alt="IM Summit Documentation 1" class="w-full h-full rounded-4xl object-cover mt-2">
                </div>

                <div class="flex flex-col gap-4 w-full lg:w-3/5">
                    <div class="flex flex-col items-center h-auto bg-main rounded-4xl gap-4 section p-10">
                        <p class="text-2xl md:text-3xl xl:text-4xl text-center">Away From Keyboard</p>
                        <p class="text-sm md:text-base xl:text-lg">
                            Aside from coding, I usually like to <span class="bg-blue-900">exercise at our dorm gym, play with friends through 
                            discord calls, and send random Instagram reels to them throughout the day</span>. These things that
                            I do outside of my career helps me keep inspired and keep thinking of new creative ways 
                            to think about things. Also, my favorite restaurant type is probably the entire samgyupsal industry.
                        </p>
                        <div class="flex flex-col xl:flex-row gap-8 w-full mt-4">
                            <img src={gym} alt="Gym" class="w-full h-70 rounded-4xl object-cover">
                            <img src={basketball} alt="Basketball" class="w-full h-70 rounded-4xl object-cover">
                        </div>
                        
                    </div>

                
                </div>
            </div>
            
            <div class="flex flex-col lg:flex-row gap-4">
                <div class="flex flex-col items-center h-auto w-full lg:w-5/8 bg-main rounded-4xl gap-4 section p-10">
                    <p class="text-2xl md:text-3xl xl:text-4xl text-center">One Big Fight</p>
                    <img src={ateneo} alt="Ateneo Logo" class="h-35 my-4 object-contain">
                    <p class="text-sm md:text-base xl:text-lg">
                        I am currently a Computer Science student at <span class="bg-blue-900">Ateneo de Manila University</span> as an <span class="bg-yellow-700">Ateneo Freshman Merit Scholar</span> 
                        (Only the top 60 out of all the passers receive this award, the highest possible distinction 
                        awarded to first-year students!).
                    </p>
                    <p class="text-sm md:text-base xl:text-lg">
                        Aside from Ateneo, I can also proudly say that I’ve passed the Big 4! 
                        These include University of the Philippines - Diliman, De La Salle University, 
                        and University of Santo Tomas, all in BS Computer Science.
                    </p>
                </div>

                <div class="flex flex-col items-center h-auto w-full lg:w-3/8 bg-main rounded-4xl gap-4 section p-10">
                    <p class="text-2xl md:text-3xl xl:text-4xl">I do orgworks too</p>
                    <img src={compsat} alt="CompSAt Logo" class="h-30 my-4 object-contain">
                    <p class="text-sm md:text-base xl:text-lg">
                        I am active in my course’s home org, <span class="bg-blue-900">The Computer Society of the Ateneo</span>
                        Here, I really try to hone my management and communication skills by working with other people 
                        by organizing events. So far, I’ve been a <span class="bg-yellow-700">Marketing Core Team</span> for Blue Hacks 2025, our org’s 
                        yearly flagship event.
                    </p>
                </div>
            </div>

            <div class="flex flex-col items-center h-auto w-full bg-main rounded-4xl gap-4 section p-10">
                <p class="text-2xl md:text-3xl xl:text-4xl">I love learning..</p>
                <p class="text-sm md:text-base xl:text-lg">
                    I really like learning new things, especially endeavors related to my field. Whether it’s 
                    through online courses, tutorials, or hands-on projects, I love exploring new topics and 
                    pushing myself to grow. I believe that staying curious and open to new ideas is the key 
                    to personal and professional growth. Here are some of the courses I've finished so far:
                </p>
            </div>

            <div class="flex flex-col lg:flex-row gap-4 w-full">
                <div class="flex flex-col items-center h-auto w-full bg-main rounded-4xl gap-4 section p-10">
                    <p class="text-3xl text-center">CS50</p>
                    <img src={cs50} alt="CS50 Logo" class="h-30 my-4 object-contain">
                    <p class="text-sm md:text-base xl:text-lg">
                        CS50's Introduction to Computer Science helped me wet my feet on CS by learning topics on
                        <span class="bg-red-900">data structures and algorithms, basic web development, databases, and basic cybersecurity</span>.
                    </p>
                </div>

                <div class="flex flex-col items-center h-auto w-full bg-main rounded-4xl gap-4 section p-10">
                    <p class="text-xl md:text-2xl xl:text-3xl text-center">ML Specialization</p>
                    <img 
                    src={deeplearning} alt="DeepLearning.AI Logo" class="h-30 my-4 object-contain">
                    <p class="text-sm md:text-base xl:text-lg">
                        The Machine Learning Specialization by Stanford and DeepLearning.AI made me aware of how
                        AI affects our present by learning topics on
                        <span class="bg-red-400">supervised, unsupervised learning, and reinforcement learning</span>.
                        
                    </p>
                </div>

                <div class="flex flex-col items-center h-auto w-full bg-main rounded-4xl gap-4 section p-10">
                    <p class="text-xl md:text-2xl xl:text-3xl text-center">The Odin Project</p>
                    <img src={odin} alt="The Odin Project Logo" class="h-30 my-4 object-contain">
                    <p class="text-sm md:text-base xl:text-lg">
                        The Odin Project has helped me learn the fundamentals of full-stack development by learning
                        <span class="bg-yellow-700">advanced HTML, CSS, and Javascript along with learning various frameworks</span>.
                    </p>
                </div>
            </div>

            

            <div class="flex flex-col items-center h-auto w-full bg-main rounded-4xl rounded-b-[4rem] gap-4 section p-10">
                <p class="text-2xl md:text-3xl xl:text-4xl text-center">..and I also like competing!</p>
                <p class="text-sm md:text-base xl:text-lg">
                    When I have the time, I also like to compete. Recently, me and a few friends have just competed in an
                    IT Business Case competition, where we were challenged to propose a solution to a real-world problem.
                    We proposed <span class="bg-blue-900">FORTRESS, a FIDO2-based risk observation, evaluation and security scoring, landing in the top 10</span>.
                </p>
                <div class="flex flex-col w-full lg:flex-row gap-8 mt-5 justify-center">
                    <img src={imsummit1} alt="IM Summit Documentation 1" class="w-full h-50 rounded-4xl object-cover">
                    <img src={imsummit2} alt="IM Summit Documentation 2" class="w-full h-50 rounded-4xl object-cover">
                </div>
                
            </div>
        </div>
    </section>
</main>



