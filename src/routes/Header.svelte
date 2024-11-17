<script lang="ts">
	import type { Snippet } from 'svelte';

	let { name, children }: { name: string; children: Snippet } = $props();
</script>

<div class="container mx-auto">
	<h1 class="text-2xl font-bold">{name ? name : 'User'}</h1>

	{@render children()}
</div>
