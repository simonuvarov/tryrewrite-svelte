<script lang="typescript">
	import { page } from '$app/stores';
	import { onMount } from 'svelte';
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

<div>
	<p>{question}</p>
	<p>{body}</p>
	<button on:click={onCheck}>Check</button>
	{#if issues}
		<pre>{JSON.stringify(issues,null,2)}</pre>
	{/if}
</div>
