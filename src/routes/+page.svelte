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
	<title>Hiroshi | Home</title>
</svelte:head>

<div class="flex flex-col lg:flex-row border rounded-xl p-4 space-x-4">
	<!-- svelte-ignore security-anchor-rel-noreferrer -->
	<a class="rounded-full" href="https://github.com/HiroshiGTakamura" target="_blank">
		<img class="h-44 md:h-44 rounded-full object-cover" src="gostosa.png" alt="" />
	</a>
	<div>
		<h1 class="text-4xl font-semibold">Pedro Hiroshi</h1>
		<div class="flex items-center">
			<h2 class="text-neutral-400 text-lg">Brasil&nbsp;</h2>
			<img
				class="h-6"
				src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/60/lg/57/flag-for-brazil_1f1e7-1f1f7.png"
				alt=""
			/>
		</div>
		<p class="text-justify">
			Cursando curso técnico de desenvolvimento de sistemas, terminando em dezembro de 2022.
		</p>
		<p>
			<!-- svelte-ignore security-anchor-rel-noreferrer -->
			Github:
			<a
				class="underline hover:no-underline hover:text-blue-500 transition-all"
				href="https://github.com/HiroshiGTakamura"
				target="_blank"
			>
				HiroshiGTakamura
			</a>
		</p>
		<p>
			<!-- svelte-ignore security-anchor-rel-noreferrer -->
			Youtube:
			<a
				class="underline hover:no-underline hover:text-blue-500 transition-all"
				href="https://www.youtube.com/channel/UCQUew3jnHtThkqsxb1m7sRA"
				target="_blank"
			>
				Hiro
			</a>
		</p>
		<div class="flex">
			Discord:&nbsp;<button
				bind:this={discordCopy}
				class="underline relative hover:no-underline hover:bg-indigo-400 rounded-md transition-all"
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
</div>

<p class="text-justify mt-2">
	<!-- bla bla bla fiz esse site por causa de nota, bla bla bla, fiz site pq achava que ia ser uma
	atividade legal pra adicionar ao trabalho bla bla bla, vamos às perguntas -->
	Nascido de uma necessidade de criar algo interessante, vontade de criar algo novo, e interesse pelas
	tecnologias envolvidas na criação de um site simples, está o site atualmente à sua frente. Gosto de
	criar coisas, e esse site não é uma exceção. Me divirto criando coisas, e vê-las, não só em seu estado
	completo, mas também durante sua produção, lentamente se tornando sua melhor versão aos meus olhos,
	por meio de ações minhas para mim sempre foi mágico.
</p>
<!-- <p>
	Ao usar esse site você concorda com o uso de cookies (pequenas informações que são salvas no seu
	computador para a facilidade do seu uso).
</p> (acontece que eu n usoi cookies, ent se eu um dia colocar algo assim nesse site eu tiro isso dos comentários) -->
<div class="mt-2">
	<a href="/questions" class="px-1 hover:bg-gray-900 bg-indigo-500 rounded-md transition-all">
		Para Questões &rarr;
	</a>
</div>
