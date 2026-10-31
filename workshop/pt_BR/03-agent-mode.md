<!-- l10n-sync: source-file="workshop/03-agent-mode.md" -->
# Parte 3: Construa o jogo com fluxos de trabalho agênticos

---

Nesta parte, o Copilot passa de planejador a implementador. Em vez de escrever código linha por linha, descreva o que você quer e deixe o Copilot trabalhar nos arquivos necessários.

## Tarefa 1: Conecte a batalha

<!-- track:vscode:start -->
1. Mude para o modo **Agent** no Copilot Chat.
2. Insira este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Retorne o Copilot CLI ao fluxo normal de programação (ou mantenha o modo autopilot se quiser que ele continue trabalhando até você interrompê-lo).
2. Se for útil, forneça contexto adicional com o arquivo `@src/pages/index.astro`.
3. Insira este prompt:
<!-- track:cli:end -->

   > Adicione JavaScript do lado do cliente à página de batalha para que:
   > 1. Ao clicar no botão Battle, obtenha os dois nomes de usuário dos campos.
   > 2. Verifique se ambos estão preenchidos e mostre um erro caso contrário.
   > 3. Busque em paralelo, pela nossa API, os dados de contribuições dos dois usuários.
   > 4. Exiba os gráficos de contribuições como grades coloridas: cada dia deve ser um quadrado colorido usando a paleta do GitHub.
   > 5. Mostre um selo VS entre os dois usuários.
   > 6. Exiba o nome de usuário, o total de contribuições e o intervalo de datas de cada usuário.
   > 7. Gerencie os estados de carregamento e os erros.
   > 8. Dispare a ação também ao pressionar Enter nos campos.
   > 9. Use a interface simples que já está estruturada.
   >
   > Use interfaces do TypeScript para a estrutura dos dados de contribuições.

<!-- track:vscode:start -->
3. Deixe o Agent Mode implementar as alterações em `index.astro`.
4. Revise as alterações propostas na visualização de diff antes de aceitá-las.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI trabalhar em `src/pages/index.astro`.
5. Inspecione as alterações geradas com `/diff` e aprove-as.
<!-- track:cli:end -->

## Tarefa 2: Teste a batalha

> **⚠️ Não está vendo as alterações?** Se a página de batalha não tiver sido atualizada, pare o servidor de desenvolvimento (`Ctrl+C`), reinicie com `npm run dev` e atualize o navegador.

1. Insira `octocat` e `torvalds` como nomes de usuário e clique em **Battle**.
2. Você deverá ver os dois gráficos de contribuições lado a lado, com grades coloridas.
3. Teste os casos de erro:
   - Deixe um ou ambos os campos vazios e clique em Battle — deverá aparecer um erro de validação.
   - Insira um nome de usuário inválido — o aplicativo deverá mostrar um erro da API.
4. Pressione **Enter** em qualquer campo — a batalha deverá começar como se você tivesse clicado no botão.

## Tarefa 3: Itere com o Copilot

Se algo não estiver exatamente certo, dê feedback diretamente ao Copilot. Por exemplo:

- *"The contribution squares are too large, make them 12x12px"*
- *"Add a hover tooltip showing the date and contribution count"*
- *"The loading state needs a pulse animation"*

<!-- track:vscode:start -->
O Agent Mode gerencia naturalmente as alterações em vários arquivos e as iterações. Cada prompt de acompanhamento usa o contexto da conversa anterior, permitindo refinar a implementação aos poucos sem começar do zero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI preservam o histórico, então cada acompanhamento se baseia no anterior. Use `/session` ou `/context` para consultar o contexto mantido pelo Copilot e `/review` após uma iteração maior para procurar erros ou melhorias.
<!-- track:cli:end -->

## Dicas para esta parte

- **Seja específico sobre o que você quer** — requisitos claros geram resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot sair do rumo.
- **Revise as alterações antes de aceitá-las** — inspecionar o código gerado é mais rápido do que reescrevê-lo.
- **Teste o aplicativo após cada etapa de implementação** para manter os problemas localizados.

## ✅ Parte 3 concluída

Você aprendeu a:

- Usar o Copilot para **implementar funcionalidades em vários arquivos**.
- **Iterar nos resultados** com feedback específico.
- Gerenciar o **ciclo completo de uma funcionalidade** — implementação, revisão, testes e refinamento.
