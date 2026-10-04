# Fluxo de intenções

O node **Classificador de intenção** categoriza a mensagem e encaminha a execução por um Switch. Classificadores especializados verificam o assunto e extraem dados necessários em determinadas rotas.

| Intenção | Tratamento observado |
| --- | --- |
| Carregamento | Verifica se a mensagem se refere a um carregamento e encaminha o tratamento associado. |
| Rotinas do WinThor | Detecta solicitações sobre rotina e aplica uma condição antes da chamada externa. |
| Derrubada de sessão | Classifica o pedido e valida a rota antes da chamada externa. |
| Chamados | Há rotas para abertura, resposta e alteração de status no GLPI. |
| Localização de usuário | Extrai o nome, consulta MySQL e organiza a resposta. |
| Pedido / liberação | Extrai o número do pedido, consulta Oracle/WinThor e usa Redis para aguardar confirmação. |
| Estoque | Extrai código do produto e filial, valida os dados e consulta Oracle/WinThor. |

O fluxo também filtra mensagens próprias, verifica menções e diferencia mensagens de grupo. Revise as rotas e as condições de autorização para cada implantação.

Os prompts foram mantidos no JSON sanitizado. Os critérios de classificação e as instruções para extrair informações estão definidos nos nodes do próprio workflow.
