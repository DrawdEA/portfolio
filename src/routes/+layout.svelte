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


