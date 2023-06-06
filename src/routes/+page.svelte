<script>
	import { ProjectCard } from '$lib/components';
	export let data;

	let filter;
</script>

<div class="">
	<h2 class="mt-2 text-center text-3xl font-bold tracking-tight text-base-content">All Projects</h2>
	<p class="text-center mt-1">Projects shared across all users.</p>

	<div class="my-10 flex justify-center px-5">
		<input
			type="text"
			placeholder="Search Projects"
			class="input input-bordered w-full max-w-md"
			bind:value={filter}
		/>
	</div>

	<div class="flex justify-center pt-4">
		<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-5">
			{#each data.projects as project}
				{#if !filter || project.name.toLowerCase().includes(filter.toLowerCase()) || project.tagline
						.toLowerCase()
						.includes(filter.toLowerCase())}
					<ProjectCard {project} />
				{/if}
			{/each}
		</div>
	</div>
</div>
