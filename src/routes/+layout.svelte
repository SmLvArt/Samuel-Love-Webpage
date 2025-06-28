<script lang="ts">
	import '../app.css';
	import Header from '$lib/Header.svelte';
	
	let { children } = $props();
</script>
<main class="page-layout">
<Header />

{@render children()}
</main>
