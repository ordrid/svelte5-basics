<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<div class="container mx-auto p-10">
	{@render children()}
</div>
