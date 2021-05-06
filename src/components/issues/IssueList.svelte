<script lang="ts">
	import type { Issue } from '../../services/paper.service';
	import IssueCard from './IssueCard.svelte';

	export let issues: Array<Issue>;

	let expandedIssueId: string;

	const expand = (issueId: string) => {
		expandedIssueId = issueId;
	};
</script>

<ul class="space-y-8">
	{#each issues as issue}
		<IssueCard {issue} expanded={issue.id === expandedIssueId} on:click={() => expand(issue.id)} />
	{/each}
</ul>
