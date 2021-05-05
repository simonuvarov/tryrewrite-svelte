<script lang="typescript">
	import type { CRITERIA_TYPE } from '../../services/paper.service';

	export let type: CRITERIA_TYPE;
	// let colors: string;

	// switch (type) {
	// 	case CRITERIA_TYPE.TA:
	// 		colors = `text-blue-600`;
	// 		break;
	// 	case CRITERIA_TYPE.CC:
	// 		colors = `text-purple-600`;
	// 		break;
	// 	case CRITERIA_TYPE.LR:
	// 		colors = `text-red-600`;
	// 		break;
	// 	case CRITERIA_TYPE.GR:
	// 		colors = `text-yellow-600`;
	// 		break;
	// }
</script>

<div>
	{type}
</div>

<style lang="postcss">
	div {
		@apply inline w-full rounded text-sm font-medium text-red-600;
	}
</style>
