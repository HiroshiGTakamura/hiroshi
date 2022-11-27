<script>
	export let title = '';
	export let style = '';
	export let date = '';
	export let file = '';
	export let desc = '';

	let table = document.getElementById('');
	let descButton = document.getElementById('');

	let paused = true;
	let isDescOpen = false;

	function clickDescription() {
		isDescOpen = !isDescOpen;
		if (isDescOpen) {
			table?.classList.add('blur');
			descButton?.classList.add('blur');
		} else {
			table?.classList.remove('blur');
			descButton?.classList.remove('blur');
		}
	}
</script>

<div class="flex items-center justify-center lg:justify-start">
	<!-- svelte-ignore a11y-click-events-have-key-events -->
	<div
		class="relative border rounded-md p-2 pt-1 w-min bg-indigo-700 hover:bg-gray-900 transition-all"
	>
		<div bind:this={table} on:click={() => (paused = !paused)}>
			<div class="flex items-center justify-between pr-1">
				<h1 class="font-semibold text-3xl">{title}</h1>
				{#if !paused}
					<svg
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="1.5"
						stroke="currentColor"
						class="w-6 h-6 animate-ping"
					>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							d="M21 12a9 9 0 11-18 0 9 9 0 0118 0z"
						/>
						<path
							stroke-linecap="round"
							stroke-linejoin="round"
							d="M15.91 11.672a.375.375 0 010 .656l-5.603 3.113a.375.375 0 01-.557-.328V8.887c0-.286.307-.466.557-.327l5.603 3.112z"
						/>
					</svg>
				{/if}
			</div>
			<div class="flex items-center justify-between">
				<h2 class="text-neutral-400">{style}</h2>
				<h2 class="text-neutral-400">{date}</h2>
			</div>
			<audio class="bg-neutral-100 rounded-md" controls controlslist="nodownload" bind:paused>
				<source src="./music/{file}.mp3" type="audio/mpeg" />
				<h1 class="bg-red-500 px-1 rounded-md">
					Desculpe, o seu browser não tem suporte para o elemento de audio.
				</h1>
			</audio>
		</div>
		<button on:click={clickDescription} bind:this={descButton} class="w-full">
			<div class="px-1 mt-2 hover:bg-gray-800 bg-indigo-500 rounded-md transition-all ">
				Descrição
			</div>
		</button>
		{#if isDescOpen}
			<div
				on:click={clickDescription}
				class="bg-white opacity-25 px-2 absolute w-full h-full top-0 left-0 rounded-md"
			/>
			<h1
				on:click={clickDescription}
				class="text-black absolute font-semibold text-justify opacity-100 top-0 left-0 mx-2"
			>
				{desc}
			</h1>
		{/if}
	</div>
</div>
