<script>
	let alaDropdown = false;
	let ala = 'Sobre Mim';

	function sobreMim() {
		ala = 'Sobre Mim';
	}

	function sobreAEscola() {
		ala = 'Sobre a Escola';
	}

	function gerais() {
		ala = 'Gerais';
	}

	function asDemais() {
		ala = 'As Demais';
	}

	function detalhes() {
		ala = 'Detalhes';
	}
</script>

<svelte:head>
	<html lang="pt-BR" />
	<title>Hiroshi | Questões</title>
</svelte:head>

<!-- PC View -->
<div class="space-x-2 lg:flex mb-2 hidden">
	{#if ala == 'Sobre Mim'}
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<h1 class="px-1 bg-gray-900 rounded-md transition-all">Sobre Mim</h1>
	{:else}
		<button
			on:click={sobreMim}
			class="px-1 hover:bg-gray-900 bg-indigo-500 rounded-md transition-all"
		>
			Sobre Mim
		</button>
	{/if}

	{#if ala == 'Sobre a Escola'}
		<h1 class="px-1 bg-gray-900 rounded-md transition-all">Sobre a Escola</h1>
	{:else}
		<button
			on:click={sobreAEscola}
			class="px-1 hover:bg-gray-900 bg-indigo-500 rounded-md transition-all"
		>
			Sobre a Escola
		</button>
	{/if}

	{#if ala == 'Gerais'}
		<h1 class="px-1 bg-gray-900 rounded-md transition-all">Gerais</h1>
	{:else}
		<button
			on:click={gerais}
			class="px-1 hover:bg-gray-900 bg-indigo-500 rounded-md transition-all"
		>
			Gerais
		</button>
	{/if}

	{#if ala == 'As Demais'}
		<h1 class="px-1 bg-gray-900 rounded-md transition-all">As Demais</h1>
	{:else}
		<button
			on:click={asDemais}
			class="px-1 hover:bg-gray-900 bg-indigo-500 rounded-md transition-all"
		>
			As Demais
		</button>
	{/if}

	{#if ala == 'Detalhes'}
		<h1 class="px-1 bg-gray-900 rounded-md transition-all">Detalhes</h1>
	{:else}
		<button
			on:click={detalhes}
			class="px-1 hover:bg-gray-900 bg-indigo-500 rounded-md transition-all"
		>
			Detalhes
		</button>
	{/if}
</div>

<!-- Mobile View -->
<div class="flex lg:hidden mb-4 items-center w-auto ">
	<button
		on:click={() => (alaDropdown = !alaDropdown)}
		class="border rounded-md px-1 flex flex-col bg-indigo-800 relative "
	>
		<div class="flex">
			<svg
				xmlns="http://www.w3.org/2000/svg"
				fill="none"
				viewBox="0 0 24 24"
				stroke-width="1.5"
				stroke="currentColor"
				class="w-8 h-8"
			>
				<path
					stroke-linecap="round"
					stroke-linejoin="round"
					d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
				/>
			</svg>
			<p class="break-keep">
				&nbsp;{ala}&nbsp;
			</p>
		</div>

		{#if alaDropdown}
			<!-- ala Dopdown -->
			<div class="absolute top-9 left-0 bg-indigo-800 flex flex-col border rounded-md w-32">
				{#if ala == 'Sobre Mim'}
					<!-- svelte-ignore a11y-click-events-have-key-events -->
					<h1 class="px-1 bg-gray-900 rounded-t-md transition-all">Sobre Mim</h1>
				{:else}
					<button on:click={sobreMim} class="px-1 hover:bg-gray-900 bg-indigo-500  transition-all">
						Sobre Mim
					</button>
				{/if}

				{#if ala == 'Sobre a Escola'}
					<h1 class="px-1 bg-gray-900  transition-all">Sobre a Escola</h1>
				{:else}
					<button
						on:click={sobreAEscola}
						class="px-1 hover:bg-gray-900 bg-indigo-500  transition-all"
					>
						Sobre a Escola
					</button>
				{/if}

				{#if ala == 'Gerais'}
					<h1 class="px-1 bg-gray-900  transition-all">Gerais</h1>
				{:else}
					<button on:click={gerais} class="px-1 hover:bg-gray-900 bg-indigo-500  transition-all">
						Gerais
					</button>
				{/if}

				{#if ala == 'As Demais'}
					<h1 class="px-1 bg-gray-900  transition-all">As Demais</h1>
				{:else}
					<button on:click={asDemais} class="px-1 hover:bg-gray-900 bg-indigo-500  transition-all">
						As Demais
					</button>
				{/if}

				{#if ala == 'Detalhes'}
					<h1 class="px-1 bg-gray-900  transition-all">Detalhes</h1>
				{:else}
					<button
						on:click={detalhes}
						class="px-1 hover:bg-gray-900 bg-indigo-500 rounded-b-md transition-all"
					>
						Detalhes
					</button>
				{/if}
			</div>
		{/if}
	</button>
</div>

{#if ala == 'Sobre Mim'}
	<div class="space-y-2">
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Qual seu MBTI?</h1>
			<p class="text-justify">
				<!-- svelte-ignore security-anchor-rel-noreferrer -->
				Meu MBTI é ENFP (NeFi). Fiz o teste
				<a
					class="text-blue-500 underline hover:text-white transition-all"
					target="_blank"
					href="https://testembti.carrd.co/">aqui</a
				>. Esse site alega ser mais preciso que o teste do
				<!-- svelte-ignore security-anchor-rel-noreferrer -->
				<a
					class="text-blue-500 underline hover:text-white transition-all"
					target="_blank"
					href="https://www.16personalities.com/">16Personalities</a
				>, que utiliza de esteriótipos imprecisos para fazer a tipagem dos usuários.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Quais suas maiores dificuldades nos estudos?</h1>
			<p class="text-justify">
				Focar, estudar conteúdo escolar frequentemente e manter conteúdo na minha mente para usar
				quando me deparo com um problema resolvido por ele.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Como você acha que aprende melhor?</h1>
			<p class="text-justify">
				Estudando consistentemente por um período de aproximadamente uma semana cada conteúdo.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">O que te desanima para ir para a escola?</h1>
			<p class="text-justify">
				Ter em mente que as aulas ou o conteúdo que serei ensinado será chato ou difícil de
				compreender.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">O que te anima a ir para a escola?</h1>
			<p class="text-justify">
				Saber que terei uma aula ou aula de um professor que gosto, e ir para interagir
				presencialmente com meus amigos.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Se pudesse somente escolher uma dessas, você seria: inteligente, rico ou feliz?
			</h1>
			<p class="text-justify">
				Inteligente, pois com devida inteligência, posso aprender a ser rico e ser feliz.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Se você fosse Deus, o que mudaria no mundo, na sociedade em que vive e nas pessoas?
			</h1>
			<p class="text-justify">
				Erradicaria a imbecilidade (não os imbecis). Humilharia governos demasiados de autoridade.
				Daria à população destes liberdade.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Que frase deixaria escrita no seu túmulo?</h1>
			<p class="text-justify">
				"Você nunca acerta o tiro que não dispara" ou "A inspiração é o combustível do artista. O
				artista cria a arte. A arte inspira o artista."
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Pretende cursar qual curso na faculdade?</h1>
			<p class="text-justify">Curso de tecnólogo em Jogos Digitais.</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Que tipo de atividades te agradam mais?</h1>
			<p class="text-justify">
				Atividades que estimulam a criatividade ou que expõem habilidades, como por exemplo,
				elaborar apresentações em vídeo.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				De 0 a 10 - Quanto apoio de sua família você tem nos seus estudos?
			</h1>
			<p class="text-justify">10. Me apoiam sempre que podem e com tudo que podem.</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				De 0 a 10 - Quanto apoio da sua família você tem em tudo?
			</h1>
			<p class="text-justify">10. Tenho apoio em tudo da minha família.</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Cite um defeito seu e uma dificuldade nos estudos.
			</h1>
			<p class="text-justify">
				Sou muito bobo e social, o que acaba atrapalhando em meios que exigem seriedade atenção e
				foco.
			</p>
		</div>
	</div>
{/if}
{#if ala == 'Sobre a Escola'}
	<div class="space-y-2">
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Quais os pontos positivos da sua escola?</h1>
			<p class="text-justify">
				A prova para a entrada faz com que as pessoas na mesma sala sejam amigáveis por pensarem de
				forma similar, e o título de técnico dado no final abre muitas oportunidades.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Quais os pontos negativos da sua escola?</h1>
			<p class="text-justify">
				Má administração, poucos professores e ensino de tecnologias desatualizadas e ineficientes.
				Por exemplo, esse site usa SvelteKit com Tailwindcss. nenhuma dessas tecnologias é ensinada
				diretamente no curso, e ambas são extremamente práticas e de alta qualidade, ganhando cada
				vez mais espaço no mercado.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Que conhecimentos você considera importantes que a escola não ensina?
			</h1>
			<p class="text-justify">
				1 • Educação financeira, pois uma grande parte da população brasileira está em dívida, mais
				<!-- svelte-ignore security-anchor-rel-noreferrer -->
				especificamente 79,3% dos lares brasileiros, segundo uma
				<a
					class="text-blue-500 underline hover:text-white transition-all"
					target="_blank"
					href="https://www.cnnbrasil.com.br/business/endividamento-atinge-80-das-familias-mais-pobres-em-setembro-um-recorde-diz-cnc/#:~:text=A%20seguir-,Endividamento%20atinge%2080%25%20das%20fam%C3%ADlias%20mais%20pobres,setembro%2C%20um%20recorde%2C%20diz%20CNC&text=O%20%C3%ADndice%20de%20fam%C3%ADlias%20endividadas,Servi%C3%A7os%20e%20Turismo%20(CNC)."
					>pesquisa da CNC de 2022</a
				>. <br />
				2 • Educação básica de vivência, como pagar uma conta, ou processar alguém. São coisas que são
				importantes para poder garantir que seus direitos não são infringidos, e que eu percebi que vou
				sair do ensino médio sem saber fazer. <br />
				3 • Educação psicóloga básica. Se todos soubermos como lidar uns com os outros, a convivência
				se torna infinitamente mais simples e pacífica.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">No que a escola poderia melhorar?</h1>
			<p class="text-justify">
				Estudando por três anos nessa escola eu nunca senti que estava sob uma forte imposição dos
				poderes daqueles hierarquicamente acima de mim, dos funcionários e principalmente dos
				alunos. Todavia, isso não é sempre o caso. Às vezes alguns funcionários da escola, mais
				especificamente acima dos professores, os que tem menos contato com os alunos, parecem
				querer impor sua dominância fazendo ameaças sobre a extensão de seus poderes, o que não
				seria um problema se fosse sempre por conta de algum aluno se rebelar. Acho que para
				melhorar a escola, deve-se haver um treinamento melhor dos funcionários para que eles saibam
				que haverá consequências se eles abusarem de seus poderes, ou alternativamente fazer esses
				funcionários terem mais contato com os alunos, fazendo uma conexão mais amigável existir
				entre eles.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Se houvesse um psicólogo na escola, você iria visitá-lo com frequência?
			</h1>
			<p class="text-justify">
				Atualmente só quero um diagnóstico profissional sobre o estado do meu mental. Só
				frequentaria com frequência se fossem necessárias várias sessões para tirar esses
				diagnósticos. Caso haja um trauma ou algo do tipo, iria querer tratar disso. Mas preferiria
				que meus problemas não fossem abertos a todos.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Como as aulas poderiam ser mais atrativas?</h1>
			<p class="text-justify">
				Simplesmente trazendo um pouco mais de entretenimento em conjunção à didática. Se eu me
				divirto enquanto assisti à aula, eu claramente estou prestando mais atenção a ela.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Você prefere o ensino integral ou turno único? Por quê?
			</h1>
			<p class="text-justify">
				Prefiro turno único. Como já é na ETEC, com turno único, eu já estou exausto. os dias que eu
				não fico sem dormir para concluir um trabalho besta só para adquirir uma nota, eu fico
				exausto e não consigo fazer as coisas que me trazem felicidade, meus hobbies por exemplo, e
				não consigo dormir sem fazer os mesmos por conta de uma sensação de inutilidade. De passar
				tanto tempo tentando fazer algo e não conseguir por conta da minha exaustão.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">É a favor de simulados periódicos?</h1>
			<p class="text-justify">
				Sim. O excesso de preparo é a melhor arma contra o despreparo. Fazer esses simulados sem
				nenhuma responsabilidade quanto à nota seria, em minha opinião, a melhor forma de trazer
				esses à escola. Assim, os alunos que não se interessam ou não vão prestar para uma faculdade
				não precisam se preocupar estudando, e aqueles que desejam, podem estudar ou só ver como as
				suas habilidades estão sem nenhum treino prévio.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Te agrada a ideia de um ensino com apostilas?
			</h1>
			<p class="text-justify">
				Sim. Assim, os ensinos passados pela escola ficam não só eternizados nessas apostilas, mas
				também será uma maravilhosa ajuda na hora dos estudos. você não só sempre poderá repassar
				conteúdos que precisa estudar ou que não entendeu por completo, como também pode resolver os
				exercícios nela. Mas não acho que elas seriam boas para auxiliar nas aulas. Fazer os
				exercícios das apostilas em aula não só é uma preguiça do professor, mas também diminui a
				quantidade de exercícios que você pode ter para estudar quando precisar depois, já que
				alguns deles já foram respondidos em aula.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Se você fosse mais ouvido sobre as decisões importantes da escola, você acha que ficaria
				mais motivado?
			</h1>
			<p class="text-justify">
				Acredito que sim, todavia, como os alunos não fazem parte de nenhuma escolha importante da
				escola, eu não faço ideia de como isso seria. Mas algo mais democrático traria uma maior
				amistosidade entre os poderes acima e os alunos, algo que eu previamente sugeri para
				melhorar a escola.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				De 0 a 10 - O quanto você acha que a escola te prepara para os vestibulares? Justifique.
			</h1>
			<p class="text-justify">
				0. Talvez 2 se fosse comprar com o ensino médio de qualquer outra escola, mas não se deve
				comprar com a preparação entre escolas, e sim o quanto o aluno deve ser preparado para o
				vestibular contra o quanto a escola realmente prepara. E a resposta final é que ela não
				prepara o aluno para o vestibular. Alguns professores tomam tempo de suas aulas para
				explicar questões do ENEM por conta própria, o que não vem como uma vontade da escola, pois
				obviamente não são todos os professores que fazem isso.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Cite três qualidades que um bom prefessor precisa ter.
			</h1>
			<p class="text-justify">
				1 • Conhecimento profundo e detalhado do tópico que ensina. <br />
				2 • Carisma e amistosidade para com seus alunos. <br />
				3 • A habilidade de entreter, interessar seus alunos pelo tópico da aula.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Cite três coisas que os professores em geral precisam melhorar.
			</h1>
			<p class="text-justify">
				1 • Melhora na interpretação das perguntas dos alunos. Vejo muito, e inclusive acontece
				bastante comigo também, que quando eu tenho uma pergunta um pouco complexa e tento a
				expressar para o professor, ele interpreta de uma forma completamente sem relação à minha
				dúvida. Não os culpo por interpretar mal as minhas perguntas, mas isso é algo recorrente
				entre múltiplos professores, se não todos. <br />
				2 • Melhora no entretenimento da aula. Volto a esse ponto, pois algo que me atrapalha muito é
				eu pessoalmente perder o foco da aula, seja por algo bobo ou por uma linha de pensamentos que
				me tiram a atenção da explicação do professor. Para mim, se eu estiver sendo entretido pela aula
				do professor, eu não perco esse foco. <br />
				3 • Melhora na amistosidade com os alunos. Isso, principalmente em comparação às outras sugestões,
				é bem mais em relação a alguns professores do que todos os professores em geral. Eu sempre sinto
				a vontade de participar da aula de um professor que é também meu amigo. Quando o professor age
				de forma fria ou de forma infantil comigo, acho um completo desrespeito, e sinto menos vontade
				de fazer qualquer coisa exigida de mim dessa matéria, mesmo sabendo que isso no final acaba apenas
				afetando a mim mesmo.
			</p>
		</div>
	</div>
{/if}

{#if ala == 'Gerais'}
	<div class="space-y-2">
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Na sua opinião, por que tantos alunos são ansiosos?
			</h1>
			<p class="text-justify">
				Infelizmente por conta do alto uso de mídias sociais e de aplicativos de conteúdo rápido,
				sempre que um acaba, há uma sugestão para um outro. Algo rápido que é anormal para a vida
				real, onde tudo depende de tempo, algo completamente desconectado da realidade por conta da
				sua velocidade surreal.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Na sua opinião, por que tantos alunos são depressivos?
			</h1>
			<p class="text-justify">
				Mídias sociais que mostram apenas o lado feliz de suas vidas. Um feliz fabricado e fora da
				realidade humana. Traz uma crença que existe uma vida em que tudo é feliz e que nada de mal
				acontece. Mas ninguém nunca lembra que a pessoa que nunca se sente triste está apenas
				vivendo metade de sua vida. <br />
				Outro fator pode ser o desencorajamento dos pais para visitar um psicólogo. É algo que nem todos
				os pais conseguem pagar, um preço incessível às massas, principalmente num país tão imundo com
				corrupção.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Você vê seu futuro como bom, razoável ou mau?
			</h1>
			<p class="text-justify">Eu ainda tenho esperanças de um futuro bom.</p>
			<p class="italic">"Trabalhe com o que você ama e nunca mais precisará trabalhar na vida."</p>
			<p class="text-justify">-Confúcio.</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Você vê a sociedade em que vive indo para uma melhora, manutenção ou piora?
			</h1>
			<p class="text-justify">
				Uma piora. Cada dia existe uma nova palavra para classificar um novo tópico que não se pode
				mais fazer piada sobre. Cada hora uma ideia mais estúpida que a anterior aparece. Cada
				minuto uma pessoa destinada à burrice nasce. Mas o pior de tudo que que cada segundo há uma
				nova criança nascendo, que pode nunca ter a liberdade que eu tenho agora para falar sobre o
				que estou falando.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Para você, qual é o maior problema do Brasil? Justifique.
			</h1>
			<p class="text-justify">
				Imbecilidade. Se as pessoas tivessem o mínimo conhecimento para saber quem merece um voto,
				nenhum presidente da última eleição teria. Com conhecimento, a pessoa estaria menos cansada.
				Ao menos um dos cidadãos se revoltaria para se tornar a mudança que quer ver. Se tornar um
				presidente que merece um voto. Se ao menos a imbecilidade fosse um mal curável.
			</p>
		</div>
	</div>
{/if}

{#if ala == 'As Demais'}
	<div class="space-y-2">
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">As três melhors perguntas:</h1>
			<div class="flex flex-col lg:flex-row lg:space-x-10">
				<div class="w-full">
					<div class="h-6 w-6 bg-yellow-500 rounded-full" />
					<p class="text-justify">
						#1 - "Se você fosse Deus, o que mudaria no mundo, na sociedade em que vive e nas
						pessoas?"
					</p>
				</div>
				<div class="w-full">
					<div class="h-6 w-6 bg-neutral-500 rounded-full" />
					<p class="text-justify">#2 - "Que frase deixaria escrita no seu túmulo?"</p>
				</div>
				<div class="w-full">
					<div class="h-6 w-6 bg-orange-700 rounded-full" />
					<p class="text-justify">
						#3 - "Se pudesse somente escolher uma dessas, você seria: inteligente, rico ou feliz?"
					</p>
				</div>
			</div>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Suas três melhores respostas:</h1>
			<div class="flex flex-col lg:flex-row lg:space-x-10">
				<div class="w-full">
					<div class="h-6 w-6 bg-yellow-500 rounded-full" />
					<p class="text-justify">
						#1 - "1 • Melhora na interpretação das perguntas dos alunos. Vejo muito, e inclusive
						acontece bastante comigo também, que quando eu tenho uma pergunta um pouco complexa e
						tento a expressar para o professor, ele interpreta de uma forma completamente sem
						relação à minha dúvida. Não os culpo por interpretar mal as minhas perguntas, mas isso é
						algo recorrente entre múltiplos professores, se não todos. <br />
						2 • Melhora no entretenimento da aula. Volto a esse ponto, pois algo que me atrapalha muito
						é eu pessoalmente perder o foco da aula, seja por algo bobo ou por uma linha de pensamentos
						que me tiram a atenção da explicação do professor. Para mim, se eu estiver sendo entretido
						pela aula do professor, eu não perco esse foco. <br />
						3 • Melhora na amistosidade com os alunos. Isso, principalmente em comparação às outras sugestões,
						é bem mais em relação a alguns professores do que todos os professores em geral. Eu sempre
						sinto vontade de participar da aula de um professor que é também meu amigo. Quando o professor
						age de forma fria ou de forma infantil comigo, acho um completo desrespeito, e sinto menos
						vontade de fazer qualquer coisa exigida de mim dessa matéria, mesmo sabendo que isso no final
						acaba apenas afetando a mim mesmo." Para a pergunta "Cite três coisas que os professores
						em geral precisam melhorar."
					</p>
				</div>
				<div class="w-full">
					<div class="h-6 w-6 bg-neutral-500 rounded-full" />
					<p class="text-justify">
						#2 - "'Você nunca acerta o tiro que não dispara" ou "A inspiração é o combustível do
						artista. O artista cria a arte. A arte inspira o artista.'" - Para a pergunta "Que frase
						deixaria escrita no seu túmulo?"
					</p>
				</div>
				<div class="w-full">
					<div class="h-6 w-6 bg-orange-700 rounded-full" />
					<p class="text-justify">
						#3 - "Eu ainda tenho esperanças de um futuro bom. <br />
						"Trabalhe com o que você ama e nunca mais precisará trabalhar na vida." <br />
						-Confúcio." - Para a pergunta "Você vê seu futuro como bom, razoável ou mau?"
					</p>
				</div>
			</div>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">
				Que outra pergunta você acha importante sere feita?
			</h1>
			<p class="text-justify">
				Que mudança na escola você acha que deveria haver, seja nos alunos, no corpo docente ou na
				infraestrutura?
			</p>
		</div>
	</div>
{/if}

{#if ala == 'Detalhes'}
	<div class="space-y-2">
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">O que é isso?</h1>
			<p class="text-justify">
				Essas são perguntas feitas em uma aula de sociologia. Aqui eu as respondo.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Para que serve esse site?</h1>
			<p class="text-justify">
				É um pouco de mim. Um pouco do que eu faço. Um pouco de como penso. Ou pensava em 2022,
				dependendo de quando você encontra esse site.
			</p>
		</div>
		<!-- <div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Quanto cusa uma comissão de música?</h1>
			<p class="text-justify">
				Vai depender muito do resultado que você espera. O preço mais baixo começa a só R$20,00! O
				preço mais barato do mercado! <a
					class="text-blue-500 underline hover:text-white transition-all"
					href="/contactme">Entre em contato agora</a
				>!
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Como eu sei se suas músicas valem a pena?</h1>
			<p class="text-justify">
				Ora, veja por si próprio! <a
					class="text-blue-500 underline hover:text-white transition-all"
					href="/mymusic">Aqui</a
				> estão algumas das minhas músicas.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Quanto cusa uma comissão de site?</h1>
			<p class="text-justify">
				Faço apenas sem back-end com banco de dados. Espere algo como esse site. O preço variará com
				a complexidade do site, e o preço inicial será R$45,00 <a
					class="text-blue-500 underline hover:text-white transition-all"
					href="/contactme">Entre em contato para mais informações</a
				>.
			</p>
		</div>
		<div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
			<h1 class="font-semibold text-2xl underline">Como eu sei se seus sites valem a pena?</h1>
			<p class="text-justify">o_o</p>
		</div> -->
	</div>
{/if}
<!-- <div class="border rounded-md p-2 bg-indigo-800 hover:bg-gray-900 transition-all">
	<h1 class="font-semibold text-2xl underline">
		
	</h1>
	<p class="text-justify">
		
	</p>
</div> -->
