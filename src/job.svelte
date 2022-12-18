<script lang="ts">
	import Caracteristic from './caracteristic.svelte';
	import LeftPart from './left-part.svelte';
	type objectTravail = {
		id: number;
		company: string;
		logo: string;
		new: boolean;
		featured: boolean;
		position: string;
		role: string;
		level: string;
		postedAt: string;
		contract: string;
		location: string;
		languages: string[];
		tools: string[];
	};
	export let travail: objectTravail;
</script>

<div
	class="flex w-[70%] justify-between shadow-[#5ba4a452] shadow-lg p-8 relative rounded-lg
    mb-10 item-job"
	style={travail.featured
		? 'background-color: hsl(180, 29%, 50%); background-size: 10%; background-repeat: no-repeat; background:linear-gradient(to right, #5ba4a4 6px, transparent 0)'
		: ''}
>
	<LeftPart
		company={travail.company}
		image={travail.logo}
		position={travail.position}
		date={travail.postedAt}
		type={travail.contract}
		location={travail.location}
		news={travail.new}
		featured={travail.featured}
	/>
	<div id="carac" class="flex items-center justify-between ">
		{#each travail.tools as tool}
			<Caracteristic name={tool} />
		{/each}
		{#if travail.level}
			<Caracteristic name={travail.level} />
		{/if}
		{#if travail.role}
			<Caracteristic name={travail.role} />
		{/if}
		{#each travail.languages as language}
			<Caracteristic name={language} />
		{/each}
	</div>
</div>
