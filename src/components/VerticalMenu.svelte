<script>
	const navigation = [
		{ name: 'Dashboard', href: '#', current: true },
		{ name: 'Settings', href: '#', current: false }
	];
</script>

<nav class="space-y-1" aria-label="Sidebar">
	{#each navigation as item}
		<a
			href={item.href}
			class="text-gray-600 hover:bg-gray-50 hover:text-gray-900 flex items-center px-3 py-2 text-sm font-medium rounded-md"
		>
			<span class="truncate">{item.name}</span>
		</a>
	{/each}
</nav>
