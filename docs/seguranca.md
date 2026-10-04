# Segurança

- Nunca versione senhas, API keys, tokens, cabeçalhos de autorização, dados de clientes ou exports sem revisão.
- Mantenha Credentials no n8n; não grave valores de autenticação no workflow ou nos arquivos de configuração.
- Use variáveis de ambiente ou um gerenciador de segredos. `.env` e variantes ficam fora do Git; `.env.example` contém apenas nomes vazios.
- Sanitize exports antes de publicar. Revise URLs, query strings, headers, identificadores de conversa e listas de autorização.
- Trate hosts internos, IDs de grupos e dados de teste como informação privada quando puderem identificar ou alcançar sistemas reais.
- Ferramentas como [gitleaks](https://github.com/gitleaks/gitleaks) ajudam a encontrar padrões de segredos; faça também revisão contextual do workflow.
- Reconfigure as Credentials no n8n após importar o JSON sanitizado.

O workflow usa `xxxxxxxxxxxxxxxxxxxx` nos valores sensíveis e nos hosts. Esses placeholders não são credenciais válidas.
