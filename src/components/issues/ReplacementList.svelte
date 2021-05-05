<script lang="ts">
	import Replacement from './Replacement.svelte';

	export let replacements: Array<string>;
</script>

<ul>
	{#each replacements as replacement}
		<Replacement {replacement} />
	{/each}
</ul>

<style lang="postcss">
	ul {
		@apply flex mt-4;
	}
</style>
