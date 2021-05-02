<script lang="typescript">
	import { onMount } from 'svelte';
	import PaperCard from '../components/PaperCard.svelte';
	import type { Paper } from '../services/paper.service';
	import paperService from '../services/paper.service';

	let papers: Array<Paper> = [];

	onMount(async () => {
		papers = (await paperService.getAllPapers()).data;
	});
</script>

<svelte:head>
	<title>Dashboard</title>
</svelte:head>

<div>
	{#each papers as paper}
		<PaperCard {paper} />
	{:else}
		<!-- this block renders when photos.length === 0 -->
		<p>loading...</p>
	{/each}
</div>
