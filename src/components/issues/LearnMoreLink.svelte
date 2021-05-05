<script lang="ts">
	export let href: string;
</script>

<a {href} target="_blank" rel="noopener noreferrer"> Learn more </a>

<style lang="postcss">
	a {
		@apply flex items-center mt-5 text-gray-400  transition-all;
		@apply text-sm leading-4 font-medium;
	}

	a:hover {
		@apply text-gray-500;
	}
</style>
