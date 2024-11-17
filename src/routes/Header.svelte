<script lang="ts">
	import type { Snippet } from 'svelte';

	let { name, children, secondChild }: { name: string; children: Snippet; secondChild: Snippet } =
		$props();
</script>

<div class="container mx-auto">
	<h1 class="text-2xl font-bold">{name ? name : 'User'}</h1>

	{@render children()}

  {@render secondChild()}
</div>
