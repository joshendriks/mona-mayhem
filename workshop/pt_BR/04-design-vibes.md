<!-- l10n-sync: source-file="workshop/04-design-vibes.md" -->
# Parte 4: Tematização orientada por design

---

Nesta parte, você vai usar os ciclos de planejamento e implementação do Copilot para projetar uma transformação visual completa. É um desenvolvimento orientado por design: comece com a visão, itere nos elementos visuais e deixe o Copilot cuidar do trabalho pesado de CSS.

## Tarefa 1: Planeje o tema retrô

<!-- track:vscode:start -->
Mude para o modo **Plan** no GitHub Copilot Chat.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Use `/plan` no GitHub Copilot CLI ou pressione **Shift+Tab** até ativar o modo de planejamento.
<!-- track:cli:end -->

Insira este prompt:

> Quero transformar esta página em uma experiência completa de fliperama retrô. Planeje uma reformulação visual abrangente que inclua: efeitos de linhas de varredura CRT no fundo, brilho de neon pulsante no título como um letreiro luminoso, emblema VS animado com mudanças de cor em gradiente, sobreposição de brilho/reflexo nos cartões de resultados dos usuários, animações de entrada flutuante nos campos, texto de carregamento que muda entre verde e roxo e efeitos de brilho ao passar o cursor sobre os quadrados de contribuição. Mantenha o fundo escuro (`#0a0a1a`) e as cores de destaque verde (`#5fed83`) e roxo (`#8a2be2`). Use um tema escuro e a fonte retrô de jogos Press Start 2P do Google Fonts.

O Copilot vai gerar um plano detalhado de implementação com todos os efeitos visuais. **Não aceite imediatamente** — revise e itere:

- Sugira ajustes na duração das animações (por exemplo: “Deixe o pulso de neon mais lento, com cerca de 3 segundos”).
- Pergunte sobre efeitos específicos (por exemplo: “Como a sobreposição de brilho dos cartões vai funcionar?”).
- Peça mudanças na abordagem se algo não parecer adequado.

## Tarefa 2: Implemente o tema

Quando estiver satisfeito com o plano, peça ao Copilot para implementá-lo.

> Implemente o plano de tema de fliperama retrô que acabamos de criar.

O Copilot vai adicionar várias animações CSS, pseudo-elementos e transições à folha de estilos. Isso pode incluir:

- `@keyframes` para linhas de varredura, pulso de neon, reflexos e efeitos de entrada flutuante
- Pseudo-elementos (`::before`, `::after`) para efeitos de sobreposição
- Propriedades personalizadas de CSS para as cores do tema
- Estados de transição e de hover para elementos interativos

<!-- track:cli:start -->
Depois que as alterações forem aplicadas, use `/diff` para revisar os estilos antes de aprová-los.
<!-- track:cli:end -->

## Tarefa 3: Refine o visual

> **⚠️ Não está vendo as alterações?** Se o novo tema ou as animações não aparecerem, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie com `npm run dev` e atualize o navegador forçadamente (`Ctrl+Shift+R`).

Mantenha a prévia do navegador aberta e itere no design. Experimente prompts como:

> O efeito de linhas de varredura está forte demais; reduza a opacidade para 0.03.

> Adicione uma cintilação elétrica sutil ao texto do título.

> O emblema VS deve pulsar de forma mais intensa.

Este é o **desenvolvimento orientado por design** — você itera no resultado visual em tempo real. Cada prompt refina a experiência até ela ficar do jeito que você quer. Não se contente com “bom o suficiente”: refine o visual até a página parecer parte de um fliperama.

## Tarefa 4: Atualize as instruções

As instruções devem refletir as principais decisões de design para manter os próximos prompts alinhados.

<!-- track:vscode:start -->
Peça ao Copilot Chat:

> Adicione ao `copilot-instructions.md` uma seção de guia de design descrevendo o tema de fliperama retrô: cores, fontes e estilo das animações.
<!-- track:vscode:end -->

<!-- track:cli:start -->
Peça ao Copilot CLI:

> Atualize as instruções do repositório com um guia curto de design para o tema de fliperama retrô: cores, fontes, estilo das animações e a regra de que a nova interface deve manter a estética neon.
<!-- track:cli:end -->

Quando a página estiver como você quer, faça commit das instruções atualizadas e das alterações de design.

## ✅ Parte 4 concluída

**O que você aprendeu:**

- Usar fluxos de planejamento para definir um **sistema de design antes da implementação**
- **Iterar no resultado visual** com prompts rápidos de acompanhamento
- **Atualizar as instruções após decisões importantes** para manter a identidade visual consistente
