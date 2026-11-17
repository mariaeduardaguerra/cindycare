# CindyCare — Critérios de aceite

## Situação

Os cenários abaixo estão planejados.
Nenhum resultado deve ser marcado como aprovado antes da execução.

Usar dados fictícios e registrar navegador, versão e data da avaliação.

## CA01 — Cadastro válido

Relacionamento: RF01, UC01, RN01.

Dado que o formulário está aberto,
quando o tutor informa nome e espécie e confirma,
então o animal deve ser cadastrado e ficar disponível para seleção.

## CA02 — Campos obrigatórios

Relacionamento: RF01, UC01, RN01.

Dado que nome ou espécie não foi preenchido,
quando o tutor tenta salvar,
então o sistema deve identificar o campo obrigatório
e não cadastrar o animal.

## CA03 — Dados opcionais inválidos

Relacionamento: RF01, RF02, UC01, UC02, RN02.

Ao informar nascimento futuro ou peso menor ou igual a zero,
o sistema deve impedir o salvamento e explicar o erro.

## CA04 — Edição de perfil

Relacionamento: RF02, UC02.

Ao editar um perfil com dados válidos,
as informações atualizadas devem aparecer no perfil
e permanecer após atualizar a página.

## CA05 — Isolamento por animal

Relacionamento: RF03 a RF11, RN03.

Dados dois animais com registros diferentes,
quando o tutor troca o animal selecionado,
então listas, histórico e painel devem mostrar somente
os registros correspondentes ao animal selecionado.

## CA06 — Datas de vacinação

Relacionamento: RF03, UC03, RN04.

- Aplicação futura deve ser rejeitada.
- Próxima dose igual ou anterior à aplicação deve ser rejeitada.
- Próxima dose vazia deve ser aceita.
- Próxima dose posterior à aplicação deve ser aceita.

## CA07 — Cadastro de tarefa recorrente

Relacionamento: RF04, UC04, RN07.

A recorrência deve aceitar apenas números inteiros maiores que zero.
Deixar a recorrência vazia deve criar uma tarefa sem repetição.

## CA08 — Conclusão e próxima ocorrência

Relacionamento: RF05, UC05, RN06 e RN07.

Dada uma tarefa com recorrência de 7 dias,
quando ela é concluída com realização em 10/12/2026,
então o registro original deve permanecer como concluído
e exatamente uma nova tarefa deve ser prevista para 17/12/2026.

A nova tarefa deve manter a recorrência de 7 dias.
A tarefa original não deve permitir uma segunda conclusão.

## CA09 — Conclusão com data futura

Relacionamento: RF05, UC05, RN06.

Uma data de realização posterior ao dia atual deve ser rejeitada,
mantendo a tarefa pendente e sem gerar nova ocorrência.

## CA10 — Identificação de atraso

Relacionamento: RF06, UC06, RN05 e RN14.

- Uma tarefa pendente de ontem deve aparecer como atrasada.
- Uma tarefa pendente de hoje não deve aparecer como atrasada.
- Uma tarefa concluída ou cancelada não deve aparecer como pendência.

## CA11 — Consulta realizada

Relacionamento: RF07, UC07, RN09.

Uma consulta com data e motivo válidos deve ser salva.
Uma consulta com data futura deve ser rejeitada.

## CA12 — Validação de despesas

Relacionamento: RF08, UC08, RN10.

- Valor zero ou negativo deve ser rejeitado.
- Valor com mais de duas casas decimais deve ser rejeitado.
- Data futura deve ser rejeitada.
- Despesa válida deve aparecer vinculada ao animal selecionado.

## CA13 — Filtros e total

Relacionamento: RF09, UC08, RN11.

Dados os registros de um mesmo animal:
- R$ 50,00 em Higiene em 01/12/2026.
- R$ 30,00 em Higiene em 31/12/2026.
- R$ 100,00 em Consulta em 15/12/2026.
- R$ 20,00 em Higiene em 30/11/2026.

Ao filtrar Higiene de 01/12/2026 a 31/12/2026,
o sistema deve mostrar dois registros e total de R$ 80,00.

Um filtro sem resultados deve mostrar R$ 0,00.
Um período com data final anterior à inicial deve ser rejeitado.

## CA14 — Histórico

Relacionamento: RF10, UC06.

O histórico do animal deve incluir suas vacinas,
consultas e tarefas concluídas.

Tarefas pendentes ou canceladas não devem aparecer
como cuidados realizados.

## CA15 — Painel mensal

Relacionamento: RF11, UC06, RN13.

O total do painel deve incluir apenas despesas do animal selecionado
no mês e ano atuais do navegador.

Despesas de outro mês ou de outro animal não devem entrar no total.

## CA16 — Edição e exclusão de registros

Relacionamento: RF12, UC09, RN12.

- Editar vacina, consulta ou despesa deve aplicar as validações originais.
- Cancelar uma exclusão deve preservar o registro.
- Confirmar deve remover o registro e atualizar listas e totais.

## CA17 — Cancelamento de tarefa recorrente

Relacionamento: RF13, UC10, RN08.

Cancelar uma tarefa pendente recorrente deve retirar essa tarefa
das pendências sem gerar uma nova ocorrência.

Tarefas concluídas e canceladas não devem permitir edição
nem reabertura nesta versão.

## CA18 — Persistência e falha de armazenamento

Relacionamento: RNF04, RN15.

Com armazenamento disponível, registros salvos devem permanecer
após atualizar a página no mesmo navegador.

Simular falha de armazenamento deve apresentar mensagem de erro,
sem indicar que a operação foi salva com sucesso.

## CA19 — Responsividade e teclado

Relacionamento: RNF01 e RNF02.

- Verificar as larguras de 360 px e 1280 px.
- A página não deve apresentar rolagem horizontal.
- Campos devem ter rótulos.
- Botões e formulários devem ser acessíveis pelo teclado.
- O elemento com foco deve ser identificável.

## CA20 — Mensagens, formatos e transparência

Relacionamento: RNF03, RNF05 e RNF06.

- Erros devem identificar o campo e explicar a correção.
- A interface deve informar o armazenamento apenas no navegador.
- Datas devem aparecer em dia/mês/ano.
- Valores devem aparecer em reais.

## CA21 — Compatibilidade e datas locais

Relacionamento: RNF07 e RN14.

Executar os fluxos principais no Chrome e no Firefox,
registrando suas versões.

Uma data informada como 10/12/2026 deve continuar sendo exibida
como 10/12/2026 depois de salvar e atualizar a página.

## Registro da execução

Preencher uma linha por cenário após testar.

| Cenário | Navegador e versão | Data | Resultado | Evidência ou observação |
|---|---|---|---|---|
| CA01 | — | — | Não executado | — |

Resultados possíveis:
- Aprovado.
- Reprovado.
- Bloqueado.
- Não executado.