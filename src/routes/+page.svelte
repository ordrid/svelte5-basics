<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { Input } from '$lib/components/ui/input';
	import { derived } from 'svelte/store';
	import Header from './Header.svelte';
	import MyForm from './MyForm.svelte';

	let name = $state('Joikrezsa');
	let status: 'open' | 'closed' = $state('open');
	let sentence = $derived(`${name} is beautiful.`);

	const onclick = () => {
		status = status === 'open' ? 'closed' : 'open';
	};
</script>

<Header {name} />

<p class="my-4 text-xl">{sentence}.</p>

<Input class="my-4 w-96" type="text" bind:value={name} />

<p class="my-4 text-xl">The store is now {status}.</p>

<Button class="mb-10" {onclick}>Toggle Status</Button>

<MyForm />
