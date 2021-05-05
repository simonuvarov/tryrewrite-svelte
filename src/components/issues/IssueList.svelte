<script lang="ts">
	import type { Issue } from '../../services/paper.service';
	import IssueCard from './IssueCard.svelte';

	export let issues: Array<Issue>;

	let expandedIssueId: string;

	const expand = (issueId: string) => {
		expandedIssueId = issueId;
	};
</script>

<ul class="space-y-8 mx-auto flex flex-col items-end px-12">
	{#each issues as issue}
		<IssueCard {issue} expanded={issue.id === expandedIssueId} on:click={() => expand(issue.id)} />
	{/each}
</ul>
