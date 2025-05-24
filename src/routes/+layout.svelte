<script lang="ts">
	import '../app.css';

	let { children } = $props();
</script>

<div class="flex flex-col items-center gap-5 bg-main h-screen bg-cover text-[#f0f0f0] font-inter font-extrabold header finisher-header">
	{@render children()}
</div>

