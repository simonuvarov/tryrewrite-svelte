<script lang="typescript">
	export let label: string;
	export let value = '';
	let className = '';
	export { className as class };
</script>

<div class={className}>
	<label for={label.toLowerCase()}>
		{label}
	</label>
	<input id={label.toLocaleLowerCase()} bind:value />
</div>

<style lang="postcss">
	label {
		@apply block text-sm text-gray-600 font-medium;
	}

	input {
		@apply block w-full px-4 py-2 border border-gray-200 rounded-md text-base leading-8
			text-gray-700 outline-none transition-shadow transition mt-2;
	}

	input:focus {
		@apply border-blue-400 ring;
	}
</style>
