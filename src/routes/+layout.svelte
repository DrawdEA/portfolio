<script lang="ts">
	import '../app.css';

	let { children } = $props();
</script>

<div class=" flex flex-col items-center h-auto bg-cover font-inter font-extrabold header finisher-header mx-auto max-w-6xl">
	{@render children()}
</div>


