<script>
	import { colors } from '$lib/colorCodes';
	let { symbol, click, center } = $props();
	function saveSelection() {
		console.log('saveSelection');
	}
</script>

<button
	class={`col-span-2 flex aspect-square w-full items-center justify-center rounded-full border-[15px] border-${colors[symbol]}-500 bg-white ${center ? 'col-start-2' : ''}`}
	onclick={click}
	id={symbol}
	><img src={`/images/icon-${symbol}.svg`} alt={symbol} />
</button>
