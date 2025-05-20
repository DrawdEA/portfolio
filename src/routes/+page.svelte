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
            duration: 1,
            stagger: 0.05,
            opacity: 0
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
        <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 xl:grid-cols-6 gap-5 items-stretch justify-stretch">
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

    <div class="flex flex-col items-center bg-[#252525] w-100% pb-50 pt-20 gap-4">
        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">Hello</p>
            <p class="text-xl">
                As an avid problem-solver, I am always on the lookout to learn new things. 
                What helps me keep motivated is that I seek to create things that can help 
                other people in various nifty ways, which is usually how I plan out my future 
                projects!
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">ROBLOX!</p>
            <p class="text-xl">
                The first time I was actually exposed to programming was back when I was in Grade 5! 
                Trying to make a quick buck, I learned the scripting language LUA through youtube tutorials 
                over the summer break. While the games I made wasn’t very fruitful, I definitely think that 
                it sparked my passion for developing and building things now.
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">Away From Keyboard</p>
            <p class="text-xl">
                Aside from coding, I usually like to exercise at our dorm gym, play with friends through 
                discord calls, and send random Instagram reels to them throughout the day. I like to think 
                that these things that I do outside of my career helps me keep inspired and keep thinking 
                of new creative ways to think about things.
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">Away From Keyboard</p>
            <p class="text-xl">
                Aside from coding, I usually like to exercise at our dorm gym, play with friends through 
                discord calls, and send random Instagram reels to them throughout the day. I like to think 
                that these things that I do outside of my career helps me keep inspired and keep thinking 
                of new creative ways to think about things.
            </p>
        </div>
        
        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">Like what you see? Let's connect!</p>
            <p class="text-xl">
                BUTTON BUTTON BUTTON
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">One Big Fight!</p>
            <p class="text-xl">
                I am currently a Computer Science at Ateneo de Manila University. I am particularly proud of this, 
                especially since I am an Ateneo Freshman Merit Scholar! (Only the top 60 out of all the passers 
                receive this award, the highest possible distinction awarded to first-year students!)
            </p>
            <p class="text-xl">
                Aside from Ateneo, I can also proudly say that I’ve passed the Big 4! 
                These include University of the Philippines - Diliman, De La Salle University, 
                and University of Santo Tomas, all in BS Computer Science! 
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">I do orgworks too</p>
            <p class="text-xl">
                As of right now, I am most active in my course’s home org, The Computer Society of the Ateneo. 
                Here, I really try to hone my management and communication skills by working with other people 
                by organizing events. So far, I’ve been a Marketing Core Team for Blue Hacks 2025, our org’s 
                yearly flagship event.
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">I love learning..</p>
            <p class="text-xl">
                I really like learning new things, especially endeavors related to my field. Whether it’s 
                through online courses, tutorials, or hands-on projects, I love exploring new topics and 
                pushing myself to grow. I believe that staying curious and open to new ideas is the key 
                to personal and professional growth. Here are some of the courses I've finished so far:
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">CS50</p>
            <p class="text-xl">
                CS50's Introduction to Computer Science
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">Machine Learning Specialization</p>
            <p class="text-xl">
                Introduction to AI
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-7/10 bg-black rounded-4xl gap-4 tool p-10">
            <p class="text-4xl 3">The Odin Project</p>
            <p class="text-xl">
                Full-Stack Development
            </p>
        </div>

        <div class="flex flex-col justify-center items-center h-auto w-auto bg-black rounded-4xl gap-4 tool p-10 mx-5">
            <p class="text-4xl 3">..and I also like competing!</p>
            <p class="text-xl">
                When I have the time, I also like to compete. Recently, me and a few friends have just competed in an
                IT Business Case competition, where we were challenged to propose a solution to a real-world problem.
                We were able to land in the top 10.
            </p>
        </div>

    </div>
</div>


