<script>
	import GameButton from '$lib/components/GameButton.svelte';

	let step = $state(1);
	let selection = $state('null');
	let selectionMachine = $state('null');
	let score = $state(0);
	let showRules = $state(false);
	let result = $state(false);

	function compareSelections() {
		if (selection === selectionMachine) {
			result = false;
		} else if (
			(selection === 'rock' && selectionMachine === 'scissors') ||
			(selection === 'scissors' && selectionMachine === 'paper') ||
			(selection === 'paper' && selectionMachine === 'rock')
		) {
			result === true && score++;
		} else {
			result === false;
		}
	}

	function saveSelection() {
		console.log(event.currentTarget);
		selection = event.currentTarget.id;
		step++;
		compareSelections();
	}
	function getRandomSelection() {
		const options = ['paper', 'rock', 'scissors'];
		return options[Math.floor(Math.random() * options.length)];
	}

	selectionMachine = getRandomSelection();

	function toggleRules() {
		showRules = !showRules;
	}
</script>

<div
	class="mx-auto flex w-full max-w-screen-lg justify-between rounded-2xl border-4 border-[#606e85] p-6"
>
	<div>
		<img src="/images/logo.svg" alt="Logo Rock Paper Scissors" />
	</div>

	<div class="w-28 rounded-md bg-white p-4">
		<div class="barlow-600 flex justify-center tracking-widest text-[#2a46c0]">Score</div>
		<div class="barlow-700 flex justify-center text-4xl text-[#3b4363]">{score}</div>
	</div>
</div>
{#if step === 1 && selection === 'null'}
	<div
		class="bg-img grid aspect-square w-full max-w-[400px] grid-cols-4 grid-rows-2 gap-[10%] bg-center"
	>
		<GameButton symbol="paper" click={saveSelection} />
		<GameButton symbol="scissors" click={saveSelection} />
		<GameButton symbol="rock" click={saveSelection} center />
	</div>
{/if}

{#if step === 2}
	<div class="flex w-[80vw] max-w-[400px] justify-between gap-8">
		<div class="flex w-[50%] flex-col items-center gap-4">
			<GameButton symbol={selection} />
			<div class="barlow-600 flex flex-col items-center text-xl tracking-widest text-white">
				YOU PICKED
			</div>
		</div>

		<div class="flex w-[50%] flex-col items-center gap-4">
			<GameButton symbol={selectionMachine} />
			<div class="barlow-600 flex flex-col items-center text-xl tracking-widest text-white">
				HOUSE PICKED
			</div>
		</div>
	</div>

	<div class="mt-8 flex w-full max-w-screen-lg justify-center">
		<div class="barlow-600 flex justify-center tracking-widest text-[#2a46c0]">
			YOU {result === true ? 'WIN' : 'LOST'}
		</div>
	</div>
{/if}

<button
	class="barlow-600 flex w-[125px] items-center justify-center rounded-lg border-2 border-[#FFF] p-2 tracking-widest text-white lg:self-end"
	onclick={toggleRules}
>
	RULES
</button>

{#if showRules}
	<div class="fixed inset-0 flex items-center justify-center bg-black bg-opacity-50">
		<div class="relative rounded-lg bg-white p-6">
			<button
				class="absolute right-4 top-4 rounded bg-red-500 p-2 text-white"
				onclick={toggleRules}
			>
				X
			</button>
			<img class="mx-auto mt-8" src="/images/image-rules.svg" alt="Rules" />
		</div>
	</div>
{/if}

<!-- {selection}
{selectionMachine} -->

<style>
	.bg-img {
		background-image: url('/images/bg-triangle.svg');
		background-size: 70%;
		background-repeat: no-repeat;
	}
</style>
