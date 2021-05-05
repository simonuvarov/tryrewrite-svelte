<script lang="typescript">
	import { page } from '$app/stores';
	import { onMount } from 'svelte';
	import IssueList from '../../components/issues/IssueList.svelte';
	import type { Issue } from '../../services/paper.service';
	import paperService from '../../services/paper.service';

	let body: string;
	let question: string;
	let issues: Array<Issue>;

	const id = $page.params.id;

	onMount(async () => {
		try {
			const res = await paperService.getPaper(id);
			question = res.data.question;
			body = res.data.body;
		} catch (error) {
			alert(error);
		}
	});

	const onCheck = async () => {
		const res = await paperService.gradePaper(id, { question, body });
		issues = res.data.issues;
	};
</script>

<div class="flex min-h-full">
	<div class="w-full" id="left">
		<p>{question}</p>
		<p>{body}</p>
		<button on:click={onCheck}>Check</button>
	</div>
	<div class="w-full h-screen" id="right">
		{#if issues}
			<IssueList {issues} />
		{/if}
	</div>
</div>

<style>
	/* Chrome, Safari and Opera */
	.no-scrollbar::-webkit-scrollbar {
		display: none;
	}

	.no-scrollbar {
		-ms-overflow-style: none; /* IE and Edge */
		scrollbar-width: none; /* Firefox */
	}
</style>
