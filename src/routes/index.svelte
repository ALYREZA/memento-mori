<script lang="ts">
	import OneYaer from '../components/OneYaer.svelte';
	import { page } from '$app/stores';
	const years = new Array(80).fill('year');
	let filled: number = 10;
	const isFilled = $page.url.searchParams.has('fill');
	if (isFilled) {
		filled = parseInt($page.url.searchParams.get('fill') || filled.toString(), 10);
	}
</script>

<div class="flex flex-1 flex-col items-center pt-10">
	<h1 class=" text-lg">ممنتو موری</h1>
	{#each years as year, ind}
		<OneYaer fill={filled} num={ind + 1} />
		{#if ind + 1 > 1 && (ind + 1) % 10 === 0}
			<div class="mb-1" />
		{/if}
	{/each}
	<h2 class=" text-base my-8">فوتر</h2>
</div>
