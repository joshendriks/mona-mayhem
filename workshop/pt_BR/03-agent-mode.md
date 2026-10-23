<!-- l10n-sync: source-file="03-agent-mode.md" -->
# Parte 3: Construa o jogo com fluxos de trabalho agênticos

---

Nesta parte, o Copilot passa do planejamento à implementação. Em vez de escrever código linha por linha, você descreve o que quer e deixa o Copilot executar o trabalho nos arquivos que precisam ser alterados.

## Tarefa 1: Conecte a Batalha

<!-- track:vscode:start -->
1. Mude para o modo **Agent** no Copilot Chat (selecione "Agent" no menu dropdown de modo).
2. Insira este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Volte o Copilot CLI ao fluxo normal de programação (ou continue no autopilot se quiser que o Copilot siga até você interrompê-lo).
2. Se for útil, mencione o arquivo da página para dar mais contexto: `@src/pages/index.astro`.
3. Insira este prompt:
<!-- track:cli:end -->

   > Adicione JavaScript do lado do cliente à página de batalha para que:
   > 1. Ao clicar no botão Battle, obtenha os nomes de usuário dos dois campos.
   > 2. Valide se ambos foram preenchidos (e exiba um erro caso contrário).
   > 3. Busque os dados de contribuições dos dois usuários em paralelo na nossa API.
   > 4. Renderize os gráficos de contribuições como grades coloridas — cada dia deve ser um quadrado colorido usando a paleta do GitHub.
   > 5. Exiba um emblema VS entre os dois usuários.
   > 6. Mostre o nome de usuário, o total de contribuições e o intervalo de datas de cada usuário.
   > 7. Trate os estados de carregamento e os erros.
   > 8. Também acione a batalha ao pressionar Enter nos campos.
   > 9. Por enquanto, use a interface simples que já está estruturada.
   >
   > Use interfaces do TypeScript para a estrutura de dados de contribuições.

<!-- track:vscode:start -->
3. Deixe o Agent Mode trabalhar na implementação em `index.astro`. Observe enquanto ele planeja sua abordagem, identifica os arquivos que precisa modificar e escreve o código.
4. Revise as alterações propostas na visualização de diff antes de aceitá-las.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI implementar a funcionalidade em `src/pages/index.astro`.
5. Use `/diff` para inspecionar as alterações geradas e aprová-las.
<!-- track:cli:end -->

## Tarefa 2: Teste a Batalha

1. Insira `octocat` e `torvalds` como os dois nomes de usuário e clique em **Battle**.
2. Você deve ver ambos os gráficos de contribuição renderizados lado a lado com grids coloridos.
3. Teste os casos de erro:
   - Deixe um ou ambos os campos vazios e clique em Battle — você deve ver um erro de validação.
   - Insira um nome de usuário inválido — o app deve exibir um erro da API.
4. Teste pressionando **Enter** em qualquer campo de entrada — deve disparar a batalha assim como clicar no botão.

## Tarefa 3: Itere com o Copilot

Se algo não estiver totalmente correto, envie comentários diretamente ao Copilot. Por exemplo:

- *"Os quadrados de contribuição estão grandes demais; deixe-os com 12x12px."*
- *"Adicione uma dica exibida ao passar o cursor, mostrando a data e a quantidade de contribuições."*
- *"O estado de carregamento precisa de uma animação pulsante."*

<!-- track:vscode:start -->
O Agent Mode lida naturalmente com alterações em vários arquivos e iterações. Cada prompt de acompanhamento aproveita o contexto anterior, permitindo refinar a implementação aos poucos sem recomeçar do zero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI mantêm o histórico, então cada prompt de acompanhamento se baseia nos anteriores. Use `/session` ou `/context` para inspecionar o contexto que o Copilot está mantendo e execute `/review` após uma iteração maior para procurar bugs ou melhorias.
<!-- track:cli:end -->

## Dicas para o Agent Mode

- **Seja específico sobre o que você quer** — requisitos claros levam a resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot sair do rumo.
- **Revise as alterações antes de aceitá-las** — código gerado é mais fácil de inspecionar do que reescrever depois.
- **Teste o app após cada implementação** para manter os problemas localizados.

## ✅ Parte 3 Concluída

Você aprendeu a:

- Usar o Copilot para **implementar alterações em vários arquivos**
- **Iterar nos resultados** com comentários específicos
- Conduzir o **ciclo completo de uma funcionalidade** — implementação, revisão, testes e refinamento
