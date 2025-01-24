<script>
	let step = $state(1);
	let selection = $state('null');
	let selectionMachine = $state('null');
	let score = $state(0);
	let showRules = $state(false);

	function saveSelection() {
		selection = event.target.id;
	}
	function getRandomSelection() {
		const options = ['paper', 'rock', 'scissors'];
		return options[Math.floor(Math.random() * options.length)];
	}

	selectionMachine = getRandomSelection();

	function compareSelections() {
		if (selection === selectionMachine) {
			console.log('Draw');
		} else if (
			0(selection === 'rock' && selectionMachine === 'scissors') ||
			(selection === 'scissors' && selectionMachine === 'paper') ||
			(selection === 'paper' && selectionMachine === 'rock')
		) {
			console.log('Win') && score++;
		} else {
			console.log('Lost');
		}
	}

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
		<button
			class="border-gradient-paper col-span-2 flex aspect-square w-full items-center justify-center rounded-full border-[15px] border-yellow-500
			bg-white"
			id="paper"
			onclick={saveSelection}><img src="/images/icon-paper.svg" alt="Paper" /></button
		>
		<button
			class="col-span-2 flex aspect-square w-full items-center justify-center rounded-full border-[15px] border-blue-500 bg-white"
			onclick={saveSelection}
			id="sciccors"><img src="/images/icon-scissors.svg" alt="Sciccors" /></button
		>
		<button
			class="col-span-2 col-start-2 flex aspect-square w-full items-center justify-center rounded-full border-[15px] border-red-500 bg-white"
			onclick={saveSelection}
			id="rock"
			><img src="/images/icon-rock.svg" alt="Rock" />
		</button>
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
		<div class="rounded-lg bg-white p-4">
			<img src="/images/image-rules.svg" alt="Rules" />
			<button class="mt-4 rounded bg-red-500 p-2 text-white" onclick={toggleRules}>X</button>
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
