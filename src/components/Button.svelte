<script lang="typescript">
	let className = '';
	export { className as class };
</script>

<button class={className}><slot /></button>

<style lang="postcss">
	button {
		@apply px-4 py-2 bg-blue-600  text-white rounded-md text-base leading-8 font-medium transition;
	}
	button:hover {
		@apply bg-blue-500;
	}
</style>
