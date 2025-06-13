<svelte:head>
  <!-- Basic Metadata -->
  <title>Edward Diesta</title>
  <meta
    name="description"
    content="Welcome to the portfolio of Edward Diesta, a passionate 
	Full-Stack Developer and Computer Science student at Ateneo de Manila. 
	Explore my projects, tech stack, and journey in software development."
  />
  <meta
    name="keywords"
    content="Software Developer, Web Developer, Philippines, Manila, Computer Science, Ateneo, Ateneo de Manila University,
	Portfolio, Full-Stack Developer, React, Next.js, HTML, CSS, JavaScript, Machine Learning, CS50, Harvard, Stanford,
	Machine Learning Specialization, DeepLearning.AI, The Odin Project, Svelte, Management Information Systems Association, MISA, CompSAt
	Computer Society of the Ateneo, Ateneo Student Residents Association, ARSA"
  />
  <meta name="author" content="Edward Diesta" />
  <meta name="publisher" content="Edward Diesta" />

  <!-- Canonical URL -->
  <link rel="canonical" href="https://diesta.dev" />

  <!-- Open Graph (for Facebook, LinkedIn, etc.) -->
  <meta property="og:type" content="website" />
  <meta property="og:locale" content="en_US" />
  <meta property="og:url" content="https://diesta.dev" />
  <meta property="og:title" content="Edward Diesta" />
  <meta
    property="og:description"
    content="Welcome to the portfolio of Edward Diesta, a passionate 
	Full-Stack Developer and Computer Science student at Ateneo de Manila. 
	Explore my projects, tech stack, and journey in software development."
  />
  <meta property="og:site_name" content="Edward Diesta Portfolio" />
  <meta
    property="og:image"
    content="https://diesta.dev/images/edward-diesta-portfolio.png"
  />
  <meta property="og:image:width" content="1200" />
  <meta property="og:image:height" content="600" />
  <meta property="og:image:alt" content="Edward Diesta Portfolio" />
  <meta property="og:image:type" content="image/jpeg" />

  <!-- Twitter Card (for Twitter/X) -->
  <meta name="twitter:card" content="summary_large_image" />
  <meta name="twitter:title" content="Edward Diesta" />
  <meta
    name="twitter:description"
    content="Welcome to the portfolio of Edward Diesta, a passionate 
	Full-Stack Developer and Computer Science student at Ateneo de Manila. 
	Explore my projects, tech stack, and journey in software development."
  />
  <meta name="twitter:creator" content="@edwarddiesta" />
  <meta
    name="twitter:image"
    content="https://diesta.dev/images/edward-diesta-portfolio.png"
  />
  <meta name="twitter:image:alt" content="Edward Diesta" />

  <!-- Robots / Search Engine Directives -->
  <meta name="robots" content="index, follow" />
  <meta
    name="googlebot"
    content="index, follow, max-snippet:-1, max-image-preview:large, max-video-preview:-1"
  />
</svelte:head>

<script lang="ts">
	import { onMount } from 'svelte';
	import '../app.css';

	interface Window {
		particlesJS: any;
	}
	
	let { children } = $props();

	onMount(() => {
		if (window.particlesJS) {
		window.particlesJS.load('particles-js', '/particles.json', function() {
			console.log('callback - particles.js config loaded');
		});
		}
	});
</script>


<div
  id="particles-js"
  class="fixed top-0 left-0 w-screen h-screen -z-10"
  style="z-index: 0;"
></div>

<div 
	class="flex flex-col items-center h-auto bg-cover font-inter font-extrabold header finisher-header mx-auto max-w-6xl" 
	style="position: relative; z-index: 1;"
>
	{@render children()}
</div>


