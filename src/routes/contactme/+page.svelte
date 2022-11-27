<script>
	// @ts-ignore
	var textCopied;
	// @ts-ignore
	var discordCopy;

	function textCopy() {
		navigator.clipboard.writeText('4Rick4#7726');
		// @ts-ignore
		discordCopy?.classList.add('bg-green-500');
		// @ts-ignore
		discordCopy?.classList.add('rounded-t-md');
		// @ts-ignore
		discordCopy?.classList.remove('rounded-md');
		// @ts-ignore
		discordCopy?.classList.remove('hover:bg-indigo-400');
		// @ts-ignore
		textCopied?.classList.remove('hidden');
		setTimeout(() => {
			// @ts-ignore
			discordCopy?.classList.remove('bg-green-500');
			// @ts-ignore
			discordCopy?.classList.remove('rounded-t-md');
			// @ts-ignore
			discordCopy?.classList.add('rounded-md');
			// @ts-ignore
			discordCopy?.classList.add('hover:bg-indigo-400');
			// @ts-ignore
			textCopied?.classList.add('hidden');
		}, 2000);
	}
</script>

<svelte:head>
	<title>Hiroshi | Entre em Contato</title>
</svelte:head>

<h1 class="fojnt-semibold text-2xl underline mb-2">
	Contate-me nas seguintes plataformas, em ordem de chance de resposta:
</h1>
<div class="space-y-4">
	<div class="flex flex-col lg:flex-row border-b">
		<p>#1 • Discord:&nbsp;</p>
		<button
			bind:this={discordCopy}
			class="underline relative w-min hover:no-underline hover:bg-indigo-400 rounded-md transition-all"
			on:click={textCopy}
		>
			4Rick4#7726
			<p
				class="bg-green-500 rounded-b-md px-1 hidden transition-all absolute"
				bind:this={textCopied}
			>
				Copiado! ✓&nbsp;
			</p>
		</button>
	</div>
	<!-- svelte-ignore security-anchor-rel-noreferrer -->
	<div class="flex flex-col lg:flex-row border-b">
		<p>#2 • Instagram:&nbsp;</p>
		<a
			class="underline hover:no-underline hover:text-blue-500 transition-all"
			target="_blank"
			href="https://www.instagram.com/ihsorih3/">@ihsorih3</a
		>
	</div>
	<div class="flex flex-col lg:flex-row border-b">
		<p>#3 • E-Mail:&nbsp;</p>
		<a
			class="underline hover:no-underline hover:text-blue-500 transition-all flex flex-col lg:flex-row"
			href="mailto:pedrohiroshigodenytakamura@gmail.com"
		>
			<p>pedrohiroshigodenytakamura</p>
			<p>@gmail.com</p>
		</a>
	</div>
</div>
