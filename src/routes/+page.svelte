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
            backgroundColor: "#121212",
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
            toggleActions: "play none none none",
            start: "top 100%",
            end: "bottom 100%",
        }});

        texttl.from(split.words, {
            y: "200%",
            autoAlpha: 0,
            stagger: 0.1,
            opacity: 0
        }).fromTo("#engineer", {
            backgroundColor: "#121212",
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
            toggleActions: "play none none none",
            start: "top 100%",
            end: "bottom 100%",
        }});

        texttl2.from(split2.words, {
            y: "200%",
            autoAlpha: 0,
            stagger: 0.1,
            opacity: 0
        }).fromTo("#create", {
            backgroundColor: "#121212",
        }, {
            backgroundColor: "#1c398e",
            duration: 0.3,
        })

        // Tools.
        let tools = gsap.utils.toArray(".tool");

        tools.forEach((tool) => {
            gsap.from(tool, {
                scrollTrigger: {
                    trigger: tool,
                    toggleActions: "play none none none",
                    start: "100% 100%",
                    end: "100% 100%",
                    scrub: 1,
                    once: true
                },

                y: "200%",
                duration: 1,
                stagger: 0.05,
                opacity: 0
            })
        })

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
</script>

<div class="text-3xl flex flex-col gap-100 mt-50 w-full items-center">
    <div class="flex max-md:flex-col gap-20 justify-center items-center">
        <div class="flex flex-col max-md:items-center">
            <p class="text-5xl sm:text-6xl md:text-7xl xl:text-8xl" id="hello">Hello,</p>
            <p class="text-3xl sm:text-4xl md:text-5xl xl:text-6xl pb-3" id="edward">I'm Edward Diesta.</p>
            <p class="text-lg sm:text-xl md:text-2xl xl:text-3xl" id="role">A <span class="bg-blue-900" id="software">Full-Stack Developer</span>.</p>
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

    <div class="flex flex-col items-center bg-[#252525] w-full pb-50 rounded-t-[4rem]">
        <div class="flex flex-col items-center w-9/10 xl:w-3/4 mx-10 gap-4">
            <img src={arrow} alt="Arrow" class="w-auto h-20 rounded-4xl object-cover mb-40">
            
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
                    <p class="text-2xl md:text-3xl xl:text-4xl text-center">ROBLOX!</p>
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
                            to think about things.
                        </p>
                        <div class="flex flex-col xl:flex-row gap-8 w-full mt-4">
                            <img src={gym} alt="Gym" class="w-full h-70 rounded-4xl object-cover">
                            <img src={basketball} alt="Basketball" class="w-full h-70 rounded-4xl object-cover">
                        </div>
                        
                    </div>

                    <div class="flex flex-col items-center h-full w-full bg-main rounded-4xl gap-4 section p-10">
                        <p class="text-2xl text-center">Like what you see? Let's connect!</p>
                        <div class="flex flex-col w-full h-full gap-4 text-3xl">
                            <div class="flex flex-col md:flex-row h-full gap-4">
                                <div class="flex items-center justify-center w-full h-full rounded-4xl object-cover text-center bg-[#4267B2]">
                                    <p>Facebook</p>
                                </div>
                                <div class="flex items-center justify-center w-full h-full rounded-4xl object-cover text-center bg-[#2b3137]">
                                    <p>GitHub</p>
                                </div>
                            </div>
                            <div class="flex flex-col md:flex-row w-full h-full gap-4">
                                <div class="flex items-center justify-center w-full h-full rounded-4xl object-cover text-center bg-[#24292e]">
                                    <p>Email</p>
                                </div>
                                <div class="flex items-center justify-center w-full h-full rounded-4xl object-cover text-center bg-[#0a66c2]">
                                    <p>LinkedIn</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            
            <div class="flex flex-col lg:flex-row gap-4">
                <div class="flex flex-col items-center h-auto w-full lg:w-5/8 bg-main rounded-4xl gap-4 section p-10">
                    <p class="text-2xl md:text-3xl xl:text-4xl text-center">One Big Fight</p>
                    <img src={ateneo} alt="Ateneo Logo" class="h-35 my-4 object-contain">
                    <p class="text-sm md:text-base xl:text-lg">
                        I am currently a Computer Science at <span class="bg-blue-900">Ateneo de Manila University</span> as an <span class="bg-yellow-700">Ateneo Freshman Merit Scholar</span> 
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
    </div>
</div>


