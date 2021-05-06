<script lang="typescript">
	import { onMount } from 'svelte';
	import PaperList from '../components/PaperList.svelte';
	import VerticalMenu from '../components/VerticalMenu.svelte';
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

<div class="flex h-screen overflow-hidden">
	<aside><VerticalMenu /></aside>
	<main><PaperList {papers} /></main>
</div>

<style lang="postcss">
	aside {
		@apply w-60 flex flex-col border-r overflow-auto bg-gray-50 px-4 pt-12;
	}

	main {
		@apply flex-1 bg-white p-10 overflow-y-auto;
	}
</style>
