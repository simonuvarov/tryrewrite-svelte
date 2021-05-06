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
	<div class="editor-pane no-scrollbar" id="left">
		<div class="w-full max-w-3xl mt-20 mx-auto">
			<p class="text-xl leading-loose font-medium text-gray-800">{question}</p>
			<p class="min-h-full space-y-5 mt-8 text-gray-800 pb-32 text-xl leading-loose">{body}</p>
			<button on:click={onCheck}>Check</button>
		</div>
	</div>
	{#if issues}
		<div class="assistant-pane no-scrollbar" id="right">
			<div class="mt-20">
				<IssueList {issues} />
			</div>
		</div>
	{/if}
</div>

<style lang="postcss">
	/* Chrome, Safari and Opera */
	.no-scrollbar::-webkit-scrollbar {
		display: none;
	}

	.no-scrollbar {
		-ms-overflow-style: none; /* IE and Edge */
		scrollbar-width: none; /* Firefox */
	}

	.editor-pane {
		@apply flex flex-grow flex-shrink-0 px-6 overflow-y-scroll h-screen;
	}

	.assistant-pane {
		@apply flex px-8 overflow-y-scroll h-screen;
	}
</style>
