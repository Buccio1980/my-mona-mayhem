<!-- l10n-sync: source-file="workshop/03-agent-mode.md" -->
# Parte 3: Construção do jogo com fluxos de trabalho agênticos

---

Nesta parte, o Copilot passa do planejamento para a implementação. Em vez de escrever código linha por linha, descreva o que você quer e deixe o Copilot realizar as alterações necessárias nos arquivos.

## Tarefa 1: Conecte a batalha

<!-- track:vscode:start -->
1. Mude para o modo **Agent** no Copilot Chat.
2. Insira este prompt:
<!-- track:vscode:end -->

<!-- track:cli:start -->
1. Volte ao fluxo de programação padrão do Copilot CLI (ou continue no modo autopilot se quiser que o Copilot prossiga até você pará-lo).
2. Se for útil, inclua o arquivo como contexto: `@src/pages/index.astro`.
3. Insira este prompt:
<!-- track:cli:end -->

   > Adicione JavaScript no lado do cliente à página de batalha para que:
   > 1. Ao clicar no botão Battle, os dois nomes de usuário sejam obtidos dos campos.
   > 2. Os dois campos sejam validados e um erro seja exibido se algum estiver vazio.
   > 3. Os dados de contribuições dos dois usuários sejam obtidos da nossa API em paralelo.
   > 4. Os gráficos de contribuições sejam exibidos como grades coloridas — cada dia é um quadrado colorido usando a paleta do GitHub.
   > 5. Um selo VS seja exibido entre os dois usuários.
   > 6. O nome de usuário, o total de contribuições e o intervalo de datas sejam exibidos para cada usuário.
   > 7. Os estados de carregamento e os erros sejam tratados.
   > 8. A ação também seja iniciada ao pressionar Enter nos campos.
   > 9. Por enquanto, use a interface simples já criada.
   >
   > Use interfaces do TypeScript para a estrutura de dados de contribuições.

<!-- track:vscode:start -->
3. Deixe o Agent Mode implementar as alterações em `index.astro`.
4. Revise as alterações propostas na visualização de diff antes de aceitá-las.
<!-- track:vscode:end -->

<!-- track:cli:start -->
4. Deixe o Copilot CLI implementar as alterações em `src/pages/index.astro`.
5. Use `/diff` para inspecionar as alterações geradas e depois aprove-as.
<!-- track:cli:end -->

## Tarefa 2: Teste a batalha

> **⚠️ Não está vendo as alterações?** Se a página de batalha não tiver sido atualizada, pare o servidor (`Ctrl+C`), reinicie com `npm run dev` e atualize o navegador.

1. Digite `octocat` e `torvalds` como os dois nomes de usuário e clique em **Battle**.
2. Você deve ver os dois gráficos de contribuições lado a lado, com grades coloridas.
3. Teste os casos de erro:
   - Deixe um ou ambos os campos vazios e clique em Battle: um erro de validação deve ser exibido.
   - Digite um nome de usuário inválido: o aplicativo deve exibir um erro da API.
4. Pressione **Enter** em qualquer campo; isso deve iniciar a batalha como se você tivesse clicado no botão.

## Tarefa 3: Itere com o Copilot

Se algo não estiver como deveria, envie comentários diretamente ao Copilot. Por exemplo:

- *“Os quadrados de contribuições estão grandes demais; ajuste para 12x12 px”*
- *“Adicione uma dica ao passar o cursor mostrando a data e a contagem de contribuições”*
- *“O estado de carregamento precisa de uma animação pulsante”*

<!-- track:vscode:start -->
O Agent Mode gerencia naturalmente as alterações em vários arquivos e as iterações. Cada prompt de acompanhamento aproveita o contexto da conversa, então você pode aprimorar a implementação aos poucos sem começar do zero.
<!-- track:vscode:end -->

<!-- track:cli:start -->
As sessões do Copilot CLI mantêm o histórico, então cada prompt de acompanhamento parte do anterior. Use `/session` ou `/context` para inspecionar o contexto que o Copilot está mantendo e `/review` após uma iteração maior para procurar bugs ou melhorias.
<!-- track:cli:end -->

## Dicas para esta parte

- **Seja específico sobre o que você quer**: requisitos claros levam a resultados melhores.
- **Divida tarefas grandes em prompts menores** se o Copilot sair do rumo.
- **Revise as alterações antes de aceitá-las**: é mais rápido inspecionar o código gerado do que reescrevê-lo depois.
- **Teste o aplicativo após cada etapa de implementação** para localizar os problemas.

## ✅ Parte 3 concluída

Você aprendeu a:

- Usar o Copilot para **implementar alterações em vários arquivos**
- **Iterar nos resultados** com comentários específicos
- Seguir o **ciclo completo de uma funcionalidade**: implementação, revisão, testes e melhorias
