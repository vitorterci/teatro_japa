# Teatro das Invenções

Projeto educativo feito para Scratch 3.0, inspirado esteticamente no teatro de bonecos japonês e organizado em quatro capítulos de história da tecnologia.

## Abrir

1. Acesse o editor Scratch 3.0 em <https://scratch.mit.edu/projects/editor/>.
2. Use **Arquivo → Carregar do seu computador** e selecione `Teatro_das_Invenções.sb3`.
3. Aguarde o carregamento dos recursos; o arquivo inclui os cenários, fantasias e sons declarados no projeto.
4. Clique na bandeira verde.

## Jogar

Na tela inicial, clique no sprite/botão de início. Siga as instruções exibidas. As respostas são digitadas como `A`, `B` ou `C` no campo de resposta do Scratch e confirmadas com Enter. Depois de cada explicação, pressione Enter quando estiver pronto para avançar. Ao fim das 12 perguntas, a tela de resultado deve aparecer; use o botão exibido para iniciar novamente.

A estrutura do projeto contém 12 perguntas em quatro grupos de três. A regra codificada no ramo de acerto adiciona 10 pontos por resposta correta; o máximo previsto é 120. Consulte `RELATORIO_DE_TESTES.md` para distinguir a inspeção dos blocos dos testes que ainda precisam ser executados no editor.

## Editar

No editor, selecione os alvos **Stage**, **Controlador**, **Interface** e os personagens para consultar cenários, lógica, falas e fantasias. A progressão principal das perguntas está no sprite `Controlador`; o palco guarda as variáveis globais. Salve uma cópia antes de modificar os blocos e exporte novamente pelo menu **Arquivo → Salvar no seu computador**.

## Recursos presentes

- 12 alvos: Stage, Controlador, Interface, Oni, Kitsune, Karakasa, Jorogumo, YukiOnna, Narrador, BotaoA, BotaoB e BotaoC.
- 8 fantasias de cenário: Tela_Inicial, Instrucoes, Capitulo_01 a Capitulo_04, Resultado e Encerramento.
- Fantasias para personagens; em Oni, Kitsune, Karakasa, Jorogumo e YukiOnna existem as expressões Neutro, Feliz e Curioso.
- Quatro sons no Controlador: abertura, acerto, erro e mudança de capítulo.
- Variáveis de palco declaradas: Ato, Sabedoria, Pergunta, Resposta, PontosPossiveis, JogoAtivo, RespostaProcessada e Fase.

## Limitações conhecidas

O arquivo foi validado como pacote ZIP com `project.json` e todas as 33 referências de mídia apontando para entradas presentes. Contudo, não foi possível confirmar a importação dentro do editor Scratch, executar o jogo a partir da bandeira, concluir uma partida nem verificar o reinício em runtime. A primeira tentativa em Scratch VM não carregou a mídia; a tentativa seguinte não avançou às perguntas e foi interrompida. Portanto, este pacote não deve ser descrito como funcionalmente validado ou como conclusão final sob o critério de jogabilidade ponta a ponta.

As alternativas são respondidas digitando letras no campo `ask and wait`; os sprites BotaoA, BotaoB e BotaoC não foram identificados como botões de resposta com scripts de clique. O projeto usa mensagens de espera para as explicações e letras exibidas nos enunciados, mas o conforto de leitura e o comportamento para entradas diferentes de A/B/C ainda precisam ser verificados no Scratch.
