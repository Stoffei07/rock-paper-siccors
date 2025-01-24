<script>
	let step = $state(2);
</script>

<div
	class="mx-auto flex w-full max-w-screen-lg justify-between rounded-2xl border-4 border-[#606e85] p-6"
>
	<div>
		<img src="/images/logo.svg" alt="Logo Rock Paper Scissors" />
	</div>

	<div class="w-28 rounded-md bg-white p-4">
		<div class="barlow-600 flex justify-center tracking-widest text-[#2a46c0]">Score</div>
		<div class="barlow-700 flex justify-center text-4xl text-[#3b4363]">12</div>
	</div>
</div>

{#if step === 1}
	<div
		class="bg-img grid aspect-square w-full max-w-[400px] grid-cols-4 grid-rows-2 gap-[10%] bg-center"
	>
		<button
			class="border-gradient-paper col-span-2 flex aspect-square w-full items-center justify-center rounded-full border-[15px] border-yellow-500
			bg-white"><img src="/images/icon-paper.svg" alt="" /></button
		>
		<button
			class="col-span-2 flex aspect-square w-full items-center justify-center rounded-full border-[15px] border-blue-500 bg-white"
			><img src="/images/icon-scissors.svg" alt="" /></button
		>
		<button
			class="col-span-2 col-start-2 flex aspect-square w-full items-center justify-center rounded-full border-[15px] border-red-500 bg-white"
			><img src="/images/icon-rock.svg" alt="" /></button
		>
	</div>
{/if}

{#if step === 2}
	<div class="flex w-[80vw] max-w-[400px] justify-between gap-8">
		<div class="flex w-[50%] flex-col items-center gap-4">
			<button
				class="mt-20 flex aspect-square w-full items-center justify-center rounded-full border-[15px]
			border-yellow-500 bg-white"><img src="/images/icon-paper.svg" alt="" /></button
			>
			<div class="barlow-600 flex flex-col items-center text-xl tracking-widest text-white">
				YOU PICKED
			</div>
		</div>
		<div class="flex w-[50%] flex-col items-center gap-4">
			<button
				class="mt-20 flex aspect-square w-full items-center justify-center rounded-full bg-[#141539] text-[#141539] opacity-45"
				>.</button
			>

			<div class="barlow-600 flex items-center text-center text-xl tracking-widest text-white">
				THE HOUSE PICKED
			</div>
		</div>
	</div>
{/if}
<!-- {#if step === 2}
	<div
		class="grid aspect-square w-full max-w-[500px] grid-cols-2 grid-rows-2 gap-[20%] gap-y-2 bg-center"
	>
		<button
			class="mt-20 flex aspect-square w-full items-center justify-center rounded-full border-[15px]
			border-yellow-500 bg-white"><img src="/images/icon-paper.svg" alt="" /></button
		>

		<button
			class="mt-20 flex aspect-square w-full items-center justify-center rounded-full border-[15px] border-blue-500 bg-white"
			><img src="/images/icon-scissors.svg" alt="" /></button
		>

		<div class="barlow-600 flex flex-col items-center text-xl tracking-widest text-white">
			YOU PICKED
		</div>
		<div class="barlow-600 flex items-center text-xl tracking-widest text-white">
			THE HOUSE PICKED
		</div>
	</div>
{/if} -->

<button
	class="barlow-600 flex w-[125px] items-center justify-center rounded-lg border-2 border-[#FFF] p-2 tracking-widest text-white lg:self-end"
>
	RULES
</button>

<style>
	.bg-img {
		background-image: url('/images/bg-triangle.svg');
		background-size: 70%;
		background-repeat: no-repeat;
	}
</style>
