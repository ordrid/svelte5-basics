<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
	import Header from './Header.svelte';

	let name = $state('Joikrezsa');
	let status: 'open' | 'closed' = $state('open');

	const onclick = () => {
		status = status === 'open' ? 'closed' : 'open';
	};
</script>

<Header {name} />

<Input class="my-4 w-96" type="text" bind:value={name} />

<p class="my-4 text-xl">The store is now {status}.</p>

<Button {onclick}>Toggle Status</Button>
