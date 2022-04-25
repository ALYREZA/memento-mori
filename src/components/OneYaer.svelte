<script lang="ts">
	import Square from './Square.svelte';

	export let num: number;
	export let fill: number;
	const weeks = new Array(52).fill('week');
</script>

<div class="flex flex-1 mt-2 relative">
	{#each weeks as wk, ind}
		<Square filled={fill >= num} />
		{#if ind + 1 > 1 && (ind + 1) % 26 === 0}
			<span class="mr-2" />
		{/if}
	{/each}
	{#if num > 1 && num % 5 === 0}
		<span class="text-xs text-gray-400 absolute -top-0 -right-2">{num}</span>
	{/if}
</div>
