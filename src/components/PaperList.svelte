<script lang="typescript">
	import type { Paper } from 'src/services/paper.service';
	import PaperCard from './PaperCard.svelte';

	export let papers: Array<Paper>;
</script>

<ul class="divide-y">
	{#each papers as paper}
		<PaperCard {paper} />
	{:else}
		<!-- this block renders when photos.length === 0 -->
		<p>loading...</p>
	{/each}
</ul>

<style>
	li {
	}
</style>
