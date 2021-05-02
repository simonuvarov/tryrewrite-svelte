<script>
	import ProsemirrorEditor from 'prosemirror-svelte';
	import { createSingleLineEditor, toPlainText } from 'prosemirror-svelte/state';

	// create the initial editor state
	let editorState = createSingleLineEditor('Hello world!');

	function handleChange(event) {
		// get the new editor state from event.detail
		editorState = event.detail.editorState;
	}

	// log the text content of the editor state, just for fun
	$: console.log(toPlainText(editorState));
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<ProsemirrorEditor
		placeholder="Go ahead and type something"
		{editorState}
		on:change={handleChange}
	/>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}
</style>
