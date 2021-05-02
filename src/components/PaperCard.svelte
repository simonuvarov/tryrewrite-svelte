<script lang="typescript">
	import type { Paper } from '../services/paper.service';

	export let paper: Paper;
</script>

<li class="hover:bg-gray-50 hover:cursor-pointer flex justify-between items-center">
	<div class="flex flex-col flex-shrink-0 py-4 px-2 max-w-lg w-full">
		<div class="font-medium truncate text-gray-800">
			{paper.question}
		</div>
		<div class="truncate mt-2 text-gray-600">{paper.body}</div>
	</div>
	<div class="flex font-medium text-gray-800 px-4">
		{parseFloat(paper.overallBand.toString()).toFixed(1)}
	</div>
</li>
