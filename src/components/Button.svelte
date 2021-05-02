<script lang="typescript">
	let className = '';
	export { className as class };
</script>

<button class={className}><slot /></button>

<style>
	button {
		display: flex;
		border-radius: 6px;
		padding-top: 8px;
		padding-bottom: 8px;
		padding-left: 16px;
		padding-right: 16px;
		font-size: 1rem;
		background-color: #2563eb;
		border: 1px solid #e5e7eb;
		color: #fff;
		line-height: 150%;
		margin-bottom: 16px;
		box-shadow: none;
		justify-content: center;
		cursor: pointer;
	}
	button:hover {
		background-color: #3b82f6;
	}
</style>
