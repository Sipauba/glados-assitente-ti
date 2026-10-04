# Arquitetura

O workflow recebe eventos do WhatsApp por meio da Evolution API e do webhook do n8n. Após filtros de mensagem e contexto, nodes com OpenAI classificam a intenção e extraem dados para as rotas operacionais. As respostas retornam pela Evolution API.

```mermaid
flowchart LR
    U[Usuário no WhatsApp] --> E[Evolution API]
    E --> W[Webhook n8n]
    W --> F[Filtros: grupo, menção e estado]
    F --> AI[OpenAI: classificação e extração]
    AI --> O[Oracle / WinThor]
    AI --> M[MySQL]
    AI --> G[GLPI]
    AI --> R[Redis]
    AI --> X[APIs externas]
    O --> E
    M --> E
    G --> E
    X --> E
```

O Redis guarda estado temporário associado a conversas que precisam de confirmação. O estado é consultado, criado e limpo pelos nodes do fluxo de pedidos, para tratar uma resposta posterior como continuação da etapa pendente.

Os endpoints foram substituídos por placeholders no export. Cada ambiente precisa configurar URLs, Credentials, destinos autorizados e parâmetros operacionais no n8n.
