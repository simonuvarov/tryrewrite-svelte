<script lang="typescript">
	import { onMount } from 'svelte';
	import PaperList from '../components/PaperList.svelte';
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
	<PaperList {papers} />
</div>
