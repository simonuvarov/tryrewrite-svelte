<script lang="typescript">
	import type { Issue } from '../../services/paper.service';
	import CriteriaLabel from './CriteriaLabel.svelte';
	import LearnMoreLink from './LearnMoreLink.svelte';
	import ReplacementList from './ReplacementList.svelte';

	export let issue: Issue;

	let expanded = false;
</script>

<li
	class:expanded
	class:collapsed={!expanded}
	on:click={() => {
		expanded = true;
	}}
>
	<CriteriaLabel type={issue.affects} />
	<div class="mt-4 space-y-1">
		<h3 class="text-lg leading-6 font-medium text-gray-800">
			{issue.shortMessage}
		</h3>
		<p class="text-base leading-7 font-normal text-gray-700">
			{issue.message}
		</p>
	</div>
	{#if issue.isInline && issue.replacements && expanded}
		<ReplacementList replacements={issue.replacements} />
	{/if}
	{#if issue.link && expanded}
		<LearnMoreLink href={issue.link} />
	{/if}
</li>

<style lang="postcss">
	.expanded {
		box-shadow: rgba(0, 0, 0, 0.16) 0px 10px 36px 0px;
	}

	.collapsed {
		box-shadow: rgba(0, 0, 0, 0.08) 0px 4px 12px;
		cursor: pointer;
	}

	li {
		@apply px-12 py-8 border border-gray-100 bg-white transition-shadow rounded-xl;
		width: 32rem;
	}
</style>
