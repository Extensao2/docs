# Permissões e Restrições — Wikipedia API
## Permissões
- API pública: Grande parte das requisições não exige autenticação.

- Para ações como edições de páginas, é necessário autenticação por login (via OAuth ou token).

## Restrições
- Rate limiting automático:

    - Wikipedia usa throttling por IP.

    - Para usuários não logados, limites são menores.

- Uso excessivo pode resultar em bloqueio temporário de IP.

- Requisições automatizadas devem se identificar com um User-Agent claro e evitar sobrecarga

- Análise de User-Agent
  - A API recomenda que você use um User-Agent personalizado e identificável (ex: nome do app + e-mail ou URL de contato).
Isso ajuda os administradores a entrar em contato em caso de uso problemático, em vez de apenas bloquear.


# Permissões e Restrições — YouTube API
##  Permissões
- Chave de API obrigatória: Necessário registrar um projeto no
Google Cloud Console para obter uma API Key.

- OAuth 2.0: Requerido para ações sensíveis (como listar vídeos de um usuário autenticado, gerenciar canais, etc).

- Escopos de acesso (scopes):

   - Leitura pública: https://www.googleapis.com/auth/youtube.readonly

   - Gerenciar uploads: https://www.googleapis.com/auth/youtube.upload

   - Gerenciar conta: https://www.googleapis.com/auth/youtube

## Restrições
- Limite de cota por dia: Cada requisição consome "pontos" (ex: uma busca consome 100 unidades; o limite padrão é 10.000 por dia).

- Quota por projeto e limites por IP.

- Algumas informações são restritas a canais verificados ou ao dono da conta autenticada.


# Open Library API (Internet Archive)
## Permissões

- Acesso público a dados de livros, autores e edições.
- Autenticação necessária apenas para ações de conta (ex: empréstimos).
Restrições

- Sem limite documentado oficialmente, mas o uso excessivo pode levar a throttling.
- Recomendado usar User-Agent identificável.
 


