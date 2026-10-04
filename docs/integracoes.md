# Integrações

| Tecnologia | Função no fluxo |
| --- | --- |
| n8n | Recebe o webhook, executa filtros, classificação, roteamento e integrações. |
| WhatsApp | Canal de conversa com o usuário. |
| Evolution API | Conecta o WhatsApp ao webhook e envia respostas. |
| OpenAI | Classifica intenções e extrai campos de mensagens. |
| Redis | Mantém estado temporário de conversas que aguardam confirmação. |
| GLPI | Abre chamados, adiciona respostas e altera status. |
| MySQL | Consulta dados usados na localização de usuários. |
| Oracle/WinThor | Consulta pedidos e estoque e aparece em uma rota de liberação de pedidos. |

O export contém referências às Credentials do n8n e URLs sanitizadas. Segredos e valores específicos do ambiente não fazem parte deste repositório. Reconfigure as integrações usando Credentials e endpoints aprovados para o ambiente de destino.
