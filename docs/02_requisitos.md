# CindyCare — Requisitos

## Contexto

CindyCare é uma marca inspirada na cachorrinha que motivou o projeto.
O sistema permite organizar os cuidados de diferentes animais.

A primeira versão considera um tutor utilizando a aplicação.
Compartilhamento entre tutores não faz parte deste escopo.

## Requisitos funcionais

| ID | Requisito | Prioridade |
|---|---|---|
| RF01 | Permitir cadastrar um animal com nome e espécie obrigatórios, além de raça, nascimento e peso opcionais. | Alta |
| RF02 | Permitir consultar e editar o perfil de um animal cadastrado. | Alta |
| RF03 | Permitir registrar vacinas com nome, data de aplicação, próxima dose opcional e observações. | Alta |
| RF04 | Permitir cadastrar tarefas de cuidado com título, animal, categoria, data prevista e recorrência opcional em dias. | Alta |
| RF05 | Permitir concluir uma tarefa informando a data de realização. | Alta |
| RF06 | Exibir tarefas pendentes por data prevista, identificando as atrasadas. | Alta |
| RF07 | Permitir registrar consultas com animal, data, motivo e observações. | Média |
| RF08 | Permitir registrar despesas com animal, descrição, categoria, data e valor. | Alta |
| RF09 | Permitir filtrar despesas por animal, categoria e período, exibindo o total dos registros encontrados. | Média |
| RF10 | Permitir consultar o histórico de vacinas, cuidados concluídos e consultas por animal. | Alta |
| RF11 | Exibir no painel os cuidados pendentes e o total de despesas do mês atual para o animal selecionado. | Média |
| RF12 | Permitir editar e excluir registros de vacinas, consultas e despesas, solicitando confirmação antes da exclusão. | Média |
| RF13 | Permitir editar ou cancelar uma tarefa pendente. | Média |

## Requisitos não funcionais

Os itens abaixo são metas de aceitação.
Ainda não representam resultados de testes executados.

| ID | Requisito | Forma de verificação |
|---|---|---|
| RNF01 | A interface deve se adaptar a telas de 360 px e 1280 px sem rolagem horizontal na página. | Inspeção nas duas larguras. |
| RNF02 | Campos de formulário devem possuir rótulos, e ações principais devem funcionar pelo teclado com foco visível. | Navegação por Tab e preenchimento dos formulários. |
| RNF03 | Mensagens de validação devem identificar o campo incorreto e explicar como corrigi-lo. | Envio de formulários com dados inválidos. |
| RNF04 | Os dados do protótipo devem permanecer disponíveis após atualizar a página no mesmo navegador, quando o armazenamento local estiver disponível. | Cadastro de um registro e atualização da página. |
| RNF05 | A interface deve informar que os dados ficam apenas no navegador e não são sincronizados entre dispositivos. | Inspeção da interface. |
| RNF06 | Datas e valores devem ser apresentados no padrão brasileiro, com despesas em reais. | Conferência dos registros exibidos. |
| RNF07 | As telas principais devem funcionar nas versões estáveis atuais de Chrome e Firefox na data da avaliação. | Execução dos cenários nos dois navegadores e registro das versões. |

## Escopo do protótipo

- Utilizar dados fictícios.
- Permitir cadastrar mais de um animal.
- Demonstrar navegação, formulários, filtros e conclusão de tarefas.
- Armazenar registros localmente no navegador.
- Não implementar login ou banco de dados remoto.
- Não enviar notificações externas.
- Não recomendar tratamentos ou intervalos de vacinação.

## Identificação dos requisitos

Cada cenário de aceitação fará referência ao requisito correspondente.
Exemplo: o cenário de cadastro de animal estará relacionado ao RF01.