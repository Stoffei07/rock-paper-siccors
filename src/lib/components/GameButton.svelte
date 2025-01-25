<script>
	import { colors } from '$lib/colorCodes';
	export let symbol;
	export let click;
	export let center = false;

	let borderColorClass = '';
	if (symbol === 'paper') borderColorClass = 'border-yellow-500';
	else if (symbol === 'scissors') borderColorClass = 'border-blue-500';
	else if (symbol === 'rock') borderColorClass = 'border-red-500';

	let centerClass = center ? 'col-start-2' : '';
</script>

<button
	class={`col-span-2 flex aspect-square w-full items-center justify-center rounded-full border-[15px] bg-white ${borderColorClass} ${centerClass}`}
	onclick={click}
	id={symbol}
>
	<img src={`/images/icon-${symbol}.svg`} alt={symbol} />
</button>
