<script lang="ts">
	import '../app.css';

	let { children } = $props();
</script>

<div class="flex flex-col items-center gap-5 bg-black h-screen bg-cover text-white font-inter font-extrabold header finisher-header">
	{@render children()}
</div>

