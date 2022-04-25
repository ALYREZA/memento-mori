<script lang="ts">
	export let filled: boolean = false;
</script>

<div class={filled ? 'bg-black' : ''} />

<style>
	div {
		height: 13px;
		width: 13px;
		border: 1px solid #999;
		border-radius: 0px;
		margin: 0 1.3px;
	}
</style>
