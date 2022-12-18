<script lang="ts">
	import Job from './job.svelte';
	import data from './data.json';
</script>

<div class="flex items-center flex-col">
	<div class="back h-[9.5rem] mb-16" />
	{#each data as travail}
		<Job {travail} />
	{/each}
</div>

<style>
	.back {
		width: 100%;
		position: static;
		top: 0;
		left: 0;
		z-index: -1;
		overflow: hidden;
		background-color: hsl(180, 29%, 50%);
		background-image: url('./images/bg-header-desktop.svg');
	}
</style>
