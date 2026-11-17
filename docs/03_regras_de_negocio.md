# CindyCare — Regras de negócio

## RN01 — Identificação do animal

Nome e espécie são obrigatórios no cadastro.
A aplicação deve gerar um identificador para cada animal.

Animais podem ter nomes iguais, pois o nome não é seu identificador.

## RN02 — Dados opcionais do perfil

Raça, data de nascimento e peso são opcionais.

Quando informados:
- O nascimento não pode estar no futuro.
- O peso deve ser maior que zero e expresso em quilogramas.

## RN03 — Vínculo dos registros

Toda vacina, tarefa, consulta e despesa deve estar vinculada
a um animal cadastrado.

Trocar o animal selecionado na interface deve atualizar
o painel, os históricos e os filtros correspondentes.

## RN04 — Registro de vacinas

O nome da vacina e a data de aplicação são obrigatórios.

A aplicação não pode estar no futuro.
A próxima dose é opcional e, quando informada, deve ser
posterior à aplicação.

A próxima dose é registrada conforme informação do tutor.
O sistema não calcula um calendário veterinário.

O registro da próxima dose aparece na área de vacinas.
Ele não cria automaticamente uma tarefa de cuidado.

## RN05 — Tarefas de cuidado

Uma tarefa deve possuir título, animal, categoria e data prevista.

Os estados possíveis são:
- Pendente.
- Concluída.
- Cancelada.

A condição "atrasada" é calculada quando a tarefa está
pendente e sua data prevista é anterior ao dia atual.

Uma tarefa prevista para hoje não é considerada atrasada.

## RN06 — Conclusão de tarefas

Somente tarefas pendentes podem ser concluídas.

A data de realização é obrigatória e não pode estar no futuro.
Concluir uma tarefa deve preservar sua data prevista original.

Uma tarefa concluída não pode ser concluída novamente.

## RN07 — Recorrência

A recorrência é opcional e deve ser um número inteiro
de dias maior que zero.

Ao concluir uma tarefa recorrente:
- O registro atual permanece no histórico como concluído.
- Uma nova tarefa pendente é criada.
- A nova data prevista é a data de realização acrescida
  do intervalo de recorrência.
- O intervalo é copiado para a nova tarefa.

Cancelar uma tarefa não gera a próxima ocorrência.
O sistema não cria antecipadamente todas as ocorrências futuras.

## RN08 — Edição e cancelamento de tarefas

Somente tarefas pendentes podem ter seus dados editados
ou seu estado alterado para cancelada.

Tarefas canceladas não aparecem entre os cuidados pendentes
e não são consideradas atrasadas.

Nesta versão, tarefas concluídas ou canceladas não podem
ser reabertas.

## RN09 — Consultas

O registro de consulta representa um atendimento já realizado.

Animal, data e motivo são obrigatórios.
A data não pode estar no futuro.

Agendamento de consultas futuras não faz parte desta versão.

## RN10 — Despesas

Uma despesa deve possuir animal, descrição, categoria,
data e valor.

O valor deve ser maior que zero e possuir no máximo
duas casas decimais.

A data não pode estar no futuro.
As despesas são registradas em reais.

## RN11 — Totalização e filtros

O total de despesas deve considerar somente os registros
que atendem aos filtros selecionados.

As datas inicial e final do período são inclusivas.
A data final não pode ser anterior à inicial.

Quando não houver registros, o total deve ser R$ 0,00.

## RN12 — Exclusão de registros

Excluir uma vacina, consulta ou despesa exige confirmação.

Cancelar a confirmação mantém o registro.
Confirmar remove o registro e atualiza a tela e os totais.

A primeira versão não possui lixeira ou recuperação
de registros excluídos.

## RN13 — Painel mensal

O total mensal corresponde às despesas do animal selecionado
com data no mês e ano atuais do navegador.

O painel deve indicar qual animal está sendo exibido.

## RN14 — Datas de calendário

As comparações de dias devem usar a data local do navegador.

Datas sem horário devem preservar o dia informado pelo tutor,
sem deslocamento causado por conversão de fuso horário.

## RN15 — Armazenamento do protótipo

Os registros ficam no navegador e dispositivo utilizados.

Limpar os dados do navegador pode remover os registros.
A aplicação não deve afirmar que os dados foram salvos
se o armazenamento falhar.