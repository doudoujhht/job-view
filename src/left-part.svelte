<script lang="ts">
	export let company: string;
	export let image: string;
	export let position: string;
	export let date: string;
	export let type: string;
	export let location: string;
	export let news: boolean;
	export let featured: boolean;
</script>

<div class="flex items-center w-[50%] shadow-none">
	<div class="image-container w-20">
		<img src={image} alt="" class="w-[100%] rounded-[50%]" />
	</div>
	<div class="w-[3rem] h-1" />
	<div class="text-container">
		<p id="company">
			{company}
			{#if news}
				<span
					class="text-white font-bold px-2 pt-1 pb-[0.125rem] ml-3 text-base rounded-xl"
					style="background-color:hsl(180, 29%, 50%);"
				>
					<span>NEW</span>
				</span>
			{/if}
			{#if featured}
				<span
					class="bg-slate-800 text-white font-bold px-2 pt-1 pb-[0.125rem] ml-3 text-base rounded-xl "
				>
					<span>FEATURED</span>
				</span>
			{/if}
		</p>
		<p class="text-xl font-bold">{position}</p>
		<div class="flex items-center text-sm lespan">
			<span>{date}</span>
			<div class="point" />
			<span>{type}</span>
			<div class="point" />
			<span>{location}</span>
		</div>
	</div>
</div>

<style>
	#company {
		font-weight: bold;
		color: hsl(180, 29%, 50%);
	}
	.point {
		display: inline-block;
		width: 4px;
		height: 4px;
		background-color: hsl(180, 8%, 52%);
		border-radius: 50%;
		margin: 0 10px;
	}
	.lespan {
		color: hsl(180, 8%, 52%);
	}
</style>
