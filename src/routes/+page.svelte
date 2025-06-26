<script lang="ts">
	import '../app.css';
	import Name from '$lib/Name.svelte';
	import { onMount } from 'svelte';
	let { children } = $props();
	let visibleWords = $state(0);
	const adjectives = ['PAINTER', 'VIDEOGRAPHER', 'LOOKER', 'THINKER', 'CONVERSATIONALIST'];

	onMount(() => {
		// Start animation after a short delay
		const timer = setTimeout(() => {
			const interval = setInterval(() => {
				visibleWords++;
				if (visibleWords >= adjectives.length) {
					clearInterval(interval);
				}
			}, 200); // 300ms delay between each word
		}, 800); // Initial delay before starting

		return () => clearTimeout(timer);
	});
</script>

<main class="page-layout">
	<div class="page-container">
		<Name />
		
		<!-- Animated subtitle -->
		<div class="flex justify-center items-center flex-wrap gap-2 mt-8 font-light text-lg tracking-wider text-stone-400">
			{#each adjectives as adjective, index}
				<span 
					class="adjective opacity-0 translate-y-2 transition-all duration-500 ease-out"
					class:visible={index < visibleWords}
                    >
					{adjective}
				</span>
				{#if index < adjectives.length - 1}
					<span class="separator opacity-0 translate-y-2 transition-all duration-500 ease-out" class:visible={index < visibleWords}>-</span>
				{/if}
			{/each}
		</div>
	</div>
</main>

<style>
	.adjective.visible,
	.separator.visible {
		opacity: 1;
		transform: translateY(0);
	}
</style>
