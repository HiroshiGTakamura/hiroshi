<script>
	import { page } from '$app/stores';
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
	<title>Hiroshi | Bem-Vindo!</title>
</svelte:head>

<div class="flex justify-center flex-col space-y-2">
	<h1 class="font-semibold text-4xl underline">Bem-Vindo!</h1>
	<p>
		Acabou de chegar? clique <a
			class="text-blue-500 underline hover:text-white transition-all"
			href="/"
		>
			aqui</a
		> para continuar.
	</p>
	<p class="text-justify">
		Se o link acima te redirecionar para cá, há uma chance que o site está inativo, com um erro
		grande ou a página que acessou não existe. Nesse caso, contate-me por <a
			class="text-blue-500 underline hover:text-white transition-all"
			href="mailto:pedrohiroshigodenytakamura@gmail.com"
		>
			e-mail</a
		> ou pelo Discord.
	</p>
	<div class="flex flex-col lg:flex-row">
		<p>Discord:&nbsp;</p>
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
</div>
