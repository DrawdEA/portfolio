<script>
  import { onMount } from "svelte";
  import { gsap } from "gsap";
  import { ScrollTrigger } from "gsap/dist/ScrollTrigger";
  import { SplitText } from "gsap/dist/SplitText";

  onMount(() => {
    // Register GSAP plugins
    gsap.registerPlugin(ScrollTrigger, SplitText);

    // --- 1. Animate the Header Text ---
    const titleSplit = new SplitText("#blog-title", { type: "words" });
    const subtitleSplit = new SplitText("#blog-subtitle", { type: "words" });

    const tl = gsap.timeline();
    tl.from(titleSplit.words, {
      opacity: 0,
      y: 30,
      duration: 0.6,
      stagger: 0.1,
      ease: "power2.out",
    }).from(
      subtitleSplit.words,
      {
        opacity: 0,
        y: 20,
        duration: 0.5,
        stagger: 0.05,
        ease: "power2.out",
      },
      "-=0.4",
    );

    // --- 2. Animate the Blog Cards on Scroll ---
    // Create a dedicated timeline for the cards
    const cardsTimeline = gsap.timeline({
      scrollTrigger: {
        trigger: "#blog-grid-section", // The section containing the cards
        start: "top 80%", // Start when the top of the section is 80% down the viewport
        toggleActions: "play none none none", // Play the timeline once and don't reverse
        once: true, // Ensures the trigger only runs one time
      },
    });

    // Add the staggered animation to the timeline
    cardsTimeline.from(".blog-card", {
      opacity: 0,
      y: 50,
      duration: 0.5,
      stagger: 0.1, // Stagger each card by 0.1s
      ease: "power2.out",
    });
  });
</script>

<main class="mt-16 px-6 text-white">
  <!-- Added id="blog-title" -->
  <h1 id="blog-title" class="text-4xl font-extrabold mb-4 text-center">
    Blogs
  </h1>
  <!-- Added id="blog-subtitle" -->
  <p id="blog-subtitle" class="text-lg mb-8 text-center">
    Web development, programming, technology, and businesses has always been
    confusing. Let's explore it together.
  </p>

  <!-- Added id="blog-grid-section" to act as the trigger -->
  <section id="blog-grid-section" class="w-full max-w-5xl mx-auto mt-12 px-4">
    <div class="grid gap-8 sm:grid-cols-2 lg:grid-cols-3">
      <!-- Blog Card 1: Added class="blog-card" -->
      <a
        href="/blog/my-first-post"
        class="blog-card block bg-[#18181b] rounded-xl shadow-lg hover:shadow-2xl transition border border-transparent hover:border-blue-600 overflow-hidden"
      >
        <div class="w-full aspect-[16/9] relative">
          <img
            src="https://picsum.photos/200/300"
            alt="My First Blog Post"
            class="object-cover w-full h-full"
          />
        </div>
        <div class="p-6">
          <h2 class="text-2xl font-bold mb-2 text-white">My First Blog Post</h2>
          <p class="text-gray-400 mb-4">
            A quick introduction to my blog and what you can expect!
          </p>
          <span class="text-blue-400 font-semibold">Read more →</span>
        </div>
        
      </a>

        <!-- Blog Card 1: Added class="blog-card" -->
      <a
        href="/blog/my-first-post"
        class="blog-card block bg-[#18181b] rounded-xl shadow-lg hover:shadow-2xl transition border border-transparent hover:border-blue-600 overflow-hidden"
      >
        <div class="w-full aspect-[16/9] relative">
          <img
            src="https://picsum.photos/200/300"
            alt="My First Blog Post"
            class="object-cover w-full h-full"
          />
        </div>
        <div class="p-6">
          <h2 class="text-2xl font-bold mb-2 text-white">My First Blog Post</h2>
          <p class="text-gray-400 mb-4">
            A quick introduction to my blog and what you can expect!
          </p>
          <span class="text-blue-400 font-semibold">Read more →</span>
        </div>
        
      </a>

        <!-- Blog Card 1: Added class="blog-card" -->
      <a
        href="/blog/my-first-post"
        class="blog-card block bg-[#18181b] rounded-xl shadow-lg hover:shadow-2xl transition border border-transparent hover:border-blue-600 overflow-hidden"
      >
        <div class="w-full aspect-[16/9] relative">
          <img
            src="https://picsum.photos/200/300"
            alt="My First Blog Post"
            class="object-cover w-full h-full"
          />
        </div>
        <div class="p-6">
          <h2 class="text-2xl font-bold mb-2 text-white">My First Blog Post</h2>
          <p class="text-gray-400 mb-4">
            A quick introduction to my blog and what you can expect!
          </p>
          <span class="text-blue-400 font-semibold">Read more →</span>
        </div>
        
      </a>

      <!-- Blog Card 2: Added class="blog-card" -->
      <a
        href="/blog/sveltekit-tips"
        class="blog-card block bg-[#18181b] rounded-xl shadow-lg hover:shadow-2xl transition border border-transparent hover:border-blue-600 overflow-hidden"
      >
        <div class="w-full aspect-[16/9] relative">
          <img
            src="https://picsum.photos/200/200"
            alt="SvelteKit Tips"
            class="object-cover w-full h-full"
          />
        </div>
        <div class="p-6">
          <h2 class="text-2xl font-bold mb-2 text-white">SvelteKit Tips</h2>
          <p class="text-gray-400 mb-4">
            My favorite tips and tricks for building fast SvelteKit apps.
          </p>
          <span class="text-blue-400 font-semibold">Read more →</span>
        </div>
      </a>

      <!-- Blog Card 3: Added class="blog-card" -->
      <a
        href="/blog/learning-fullstack"
        class="blog-card block bg-[#18181b] rounded-xl shadow-lg hover:shadow-2xl transition border border-transparent hover:border-blue-600 overflow-hidden"
      >
        <div class="w-full aspect-[16/9] relative">
          <img
            src="https://picsum.photos/500/300"
            alt="Learning Full-Stack"
            class="object-cover w-full h-full"
          />
        </div>
        <div class="p-6">
          <h2 class="text-2xl font-bold mb-2 text-white">Learning Full-Stack</h2>
          <p class="text-gray-400 mb-4">
            How I approach learning both frontend and backend development.
          </p>
          <span class="text-blue-400 font-semibold">Read more →</span>
        </div>
      </a>
      <!-- Add more blog cards here with the class="blog-card" -->
    </div>
  </section>
</main>