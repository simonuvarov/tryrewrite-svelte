<script lang="typescript">
	export let value = '';
	let className = '';
	export { className as class };
</script>

<input bind:value class={className} />

<style>
	input {
		display: flex;
		border-radius: 6px;
		padding-top: 8px;
		padding-bottom: 8px;
		padding-left: 16px;
		padding-right: 16px;
		font-size: 1rem;
		background-color: white;
		border: 1px solid #e5e7eb;
		color: #374151;
		line-height: 150%;
		margin-bottom: 16px;
		box-shadow: none;
	}
</style>
