<svelte:head>
	<title>Rewrite: IELTS writing toolkit</title>
</svelte:head>

<section class="bg-white w-full pt-20 pb-44 px-4 flex flex-col items-center">
	<h1>Write. Check. Correct. Repeat.</h1>
	<p>Get instant feedback and track your progress – all in one place</p>
	<a class="mt-10	px-4	py-2 cta" href="/signup"> Get started now </a>
</section>

<style lang="postcss">
	h1 {
		@apply text-7xl font-extrabold tracking-tight text-gray-800 max-w-xl text-center;
	}

	p {
		@apply text-2xl mt-6 text-gray-500 max-w-3xl text-center;
	}

	.cta {
		@apply bg-blue-600 text-white	rounded-md font-medium text-base leading-8 transition	outline-none;
	}

	.cta:hover {
		@apply bg-blue-500;
	}
</style>
