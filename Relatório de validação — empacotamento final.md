# Relatório de validação — empacotamento final

**Resultado:** pacote construído e validado estruturalmente; importação e jogabilidade de ponta a ponta não confirmadas. Não declarar o jogo concluído sob o critério funcional solicitado até que os testes marcados como pendentes sejam executados no Scratch 3.0.

## Validação técnica executada

| Verificação | Resultado observado | Status |
|---|---|---|
| Arquivo `.sb3` criado com o nome de entrega | `Teatro_das_Invenções.sb3` existe; 493.405 bytes | Aprovado |
| Integridade ZIP | `zipfile.testzip()` retornou `None` | Aprovado |
| `project.json` | Presente e interpretável como JSON; 97.402 bytes | Aprovado |
| Arquivos de mídia | 33 referências entre fantasias e sons; todas correspondem a entradas do arquivo | Aprovado |
| Estrutura de sprites | 12 alvos, incluindo palco, controlador, interface, cinco personagens, narrador e três sprites de alternativa | Aprovado estruturalmente |
| Fantasias e cenários | 8 fantasias de palco, cinco sprites de personagens com três expressões declaradas cada | Aprovado estruturalmente |
| Variáveis | Ato, Sabedoria, Pergunta, Resposta, PontosPossiveis, JogoAtivo, RespostaProcessada e Fase presentes no palco | Aprovado estruturalmente |
| Perguntas e alternativas | 12 blocos `ask and wait` com enunciados iniciados por A/B/C encontrados | Aprovado estruturalmente |
| Importação no editor Scratch 3.0 | O editor web não foi aberto nem usado nesta sessão | Não testado |
| Execução desde a bandeira verde | Não observada no Scratch editor. Tentativa VM não iniciou o fluxo esperado | Não testado |
| Partida completa | Não concluída | Não testado |
| Reinício e pontuação zero | Blocos de zeragem existem, mas o reinício em execução não foi verificado | Não testado |

## Testes funcionais solicitados

| ID | Procedimento | Esperado | Observado | Status | Correção/ação |
|---|---|---|---|---|---|
| F01 | Bandeira verde | Inicializa variáveis e tela inicial | Script declarado no Stage; execução real pendente | Não testado | Executar no Scratch |
| F02 | Tela inicial | Cenário e botão visíveis | Fantasia e sprite existem; renderização não confirmada | Não testado | Conferir no editor |
| F03 | Clique em iniciar | Dispara início da partida | Bloco de clique em Interface transmite `iniciar_jogo`; clique real não executado | Não testado | Testar no palco |
| F04 | Progressão | Quatro capítulos acessíveis | Blocos de troca para os quatro cenários encontrados; progressão não executada | Não testado | Completar uma partida |
| F05 | Três perguntas por ato | 12 perguntas em 4 grupos de 3 | Sequência de 12 enunciados encontrada na inspeção | Aprovado estruturalmente; runtime pendente | Conferir execução |
| F06 | Três alternativas por pergunta | A/B/C legíveis | Textos A/B/C presentes em cada pergunta; legibilidade em palco pendente | Aprovado estruturalmente; runtime pendente | Verificar tamanho real |
| F07 | Registro da alternativa | Resposta digitada avaliada corretamente | Cada etapa compara `sensing_answer` com uma letra; nenhum caso foi rodado | Não testado | Testar A/B/C em todas as questões |
| F08 | Feedback | Acerto e erro recebem mensagens distintas | Ramo de acerto e ramo de erro contêm falas e broadcasts diferentes | Aprovado estruturalmente; runtime pendente | Observar no editor |
| F09 | Pontuação uma vez | +10 por acerto, 0 por erro | Incremento de 10 presente no ramo correto; concorrência/repetição não testada | Não testado | Rodar matrizes de pontuação |
| F10 | Expressões | Reação apropriada ao acerto/erro | Scripts de reação selecionam fantasias Feliz/Curioso; exibição pendente | Aprovado estruturalmente; runtime pendente | Conferir sprites visíveis |
| F11 | Explicações | Permanecem até jogador avançar | Cada explicação antecede um `ask and wait` de continuação; leitura real pendente | Não testado | Conferir pausa e texto |
| F12 | Transições | Só avançar após confirmação | Prompt de continuação aparece antes do próximo grupo no script; execução pendente | Não testado | Jogar e conferir ordem |
| F13 | Resultado | Tela final mostra pontuação/resultados | Há troca para cenário Resultado e mensagem de fim; execução pendente | Não testado | Concluir uma partida |
| F14 | Reinício | Pontuação/estado zerados | Receptor `reiniciar_jogo` zera variáveis principais; acionamento não verificado | Não testado | Reiniciar após jogar |
| F15 | Controles inativos | Sem ação indevida durante a partida | Interface se esconde após clique inicial e reaparece no fim segundo scripts; cliques repetidos não testados | Não testado | Testar em runtime |
| F16 | Pergunta sem travar | Entradas/continuação avançam corretamente | `ask and wait` exige entrada; validação de letras fora de A/B/C não encontrada | Não testado | Verificar entrada inválida e corrigir se reproduzido |
| F17 | Sprites essenciais | Personagens necessários permanecem visíveis | Mensagens mostrar/ocultar encontradas; estado real não observado | Não testado | Percorrer todos os atos |
| F18 | Mídia | Cenários/fantasias/sons carregam | Referências todas presentes no ZIP; carregamento Scratch ainda não confirmado | Aprovado estruturalmente; runtime pendente | Importar e conferir áudio/arte |
| F19 | Editabilidade | Scripts podem ser alterados no editor Scratch | Projeto JSON lido; editor não abriu o pacote | Não testado | Importar no Scratch 3.0 |
| F20 | Exportar/reimportar | Reimportação preserva o jogo | ZIP validado; ciclo pelo editor não feito | Não testado | Exportar e reimportar no Scratch |

## Pontuação

| Cenário | Esperado | Observado | Status |
|---|---:|---|---|
| 12 respostas certas | 120 | Regra de +10 aparece no ramo correto; execução não feita | Não testado |
| 12 respostas erradas | 0 | Não encontrei incremento no ramo de erro; execução não feita | Não testado |
| Alternância de resultados | 10 por acerto | Não executada | Não testado |
| Cliques/entradas repetidos | Sem duplicação | Não executados | Não testado |
| Reiniciar | 0 | Bloco de reset está presente; resultado real pendente | Não testado |

## Tentativas de execução

A tentativa inicial de Scratch VM carregou a estrutura de alvos, mas alertou que não havia armazenamento configurado para as mídias e não chegou a disparar perguntas. Após configurar o armazenamento, o harness ainda não recebeu perguntas e ficou sem progresso; foi interrompido. Isso não constitui teste do jogo, nem prova que o projeto falha no Scratch oficial.

## Limitações e pendências

- Não há confirmação de importação no editor Scratch 3.0 nem de partida jogável de ponta a ponta.
- A pontuação, os feedbacks, os sons, as expressões e o reinício foram inspecionados nos blocos, mas não verificados em runtime.
- A resposta é digitada no campo de `ask and wait`; `BotaoA`, `BotaoB` e `BotaoC` não foram encontrados com scripts próprios de clique.
- Entradas que não sejam A/B/C não têm validação explícita identificada; testar no editor antes de corrigir.
- A documentação histórica identifica ausência de referências específicas para algumas alegações do capítulo de máquinas.
- A tentativa em VM não substitui teste manual pelo editor oficial.
