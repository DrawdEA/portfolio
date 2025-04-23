<script lang="ts">
	import '../app.css';

	let { children } = $props();
</script>

<div class="flex flex-col items-center gap-5 bg-black h-screen bg-cover overflow-auto text-white font-inter font-extrabold">
	{@render children()}
</div>

