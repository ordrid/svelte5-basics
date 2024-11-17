<script lang="ts">
	import Button from '$lib/components/ui/button/button.svelte';
	import Input from '$lib/components/ui/input/input.svelte';
	import Label from '$lib/components/ui/label/label.svelte';

	let formState: { name: string; birthday: string; step: number; error: string } = $state({
		name: '',
		birthday: '',
		step: 0,
		error: ''
	});
</script>

<main>
	<p class="text-xl">Step: {formState.step + 1}</p>

	{#if formState.error}
		<p class="text-red-500">
			{formState.error}
		</p>
	{/if}

	{@render formStep({ question: "What's your name", id: 'name', type: 'text' })}
</main>

{#snippet formStep({ question, id, type }: { type: string; id: string; question: string })}
	<article>
		<div>
			<Label for={id}>{question}</Label>
			<Input {type} {id} bind:value={formState[id]} />
		</div>
	</article>
{/snippet}
