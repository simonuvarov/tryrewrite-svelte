<script lang="typescript">
	import type { Paper } from '../services/paper.service';

	export let paper: Paper;
</script>

<li>
	<a href={`/paper/${paper.id}`}>
		<div class="flex flex-col flex-shrink-0 py-4 px-2 max-w-lg w-full">
			<div class="question">
				{paper.question}
			</div>
			<div class="body mt-2">{paper.body}</div>
		</div>
		<div class="score px-4">
			{parseFloat(paper.overallBand.toString()).toFixed(1)}
		</div>
	</a>
</li>

<style lang="postcss">
	a {
		@apply cursor-pointer flex justify-between items-center;
	}

	a:hover {
		@apply bg-gray-50;
	}

	.question {
		@apply font-medium truncate text-gray-800;
	}

	.body {
		@apply truncate text-gray-600;
	}

	.score {
		@apply flex font-medium text-gray-800;
	}
</style>
