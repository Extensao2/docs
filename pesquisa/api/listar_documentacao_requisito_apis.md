
# Youtube:

## Documentação:
https://developers.google.com/youtube/v3/docs?apix=true&hl=pt-br

## Requisitos:
- [Criar um projeto no Google Cloud](https://console.cloud.google.com/projectcreate?previousPage=%2Fapis%2Fdashboard%3Fhl%3Dpt-br%26invt%3DAbv9bQ%26project%3Dtrue-bit-458210-u5%26supportedpurview%3Dproject&organizationId=0&hl=pt-br&invt=Abv9bQ&supportedpurview=project)
- [Ativar recurso de YouTube Data API v3](https://console.cloud.google.com/apis/library/youtube.googleapis.com?hl=pt-br&invt=Abv9bQ&project=true-bit-458210-u5&supportedpurview=project)
- Enviar chave de api, ou OAuth 2.0, como parâmetro em cada requisição.

## Limitações:
- Possui limitação de requisições diárias de 10.000 cotas.
	- [Página com custo de cada operação](https://developers.google.com/youtube/v3/determine_quota_cost?hl=pt-br)

# Wikipedia:

## Documentação:
https://www.mediawiki.org/wiki/API:Main_page/pt-br

## Requisitos:
Não possui.

## Limitações:
Não encontrado.



# News API
## Documentação:

https://newsapi.org/docs

## Requisitos:

Criar uma conta gratuita em: https://newsapi.org/register
Gerar uma API Key
Enviar a chave como parâmetro apiKey em todas as requisições REST

## Parâmetros úteis para português / Brasil:

language=pt → Garante apenas notícias em português
country=br → Garante fontes do Brasil
q=educação ou outro termo → Foco no tema desejado
category=education não funciona no Brasil (somente para certos países)


## Limitações do plano gratuito da News API:

- Número de requisições: Limitado a 100 requisições por dia.
- Fontes permitidas: Somente fontes pré-aprovadas pela News API. Você não pode usar qualquer site de notícias externo.
- Uso comercial: Não é permitido utilizar o plano gratuito para fins comerciais ou em produtos voltados ao mercado.
- Acesso ao conteúdo: A API retorna apenas os títulos, descrições, URLs e outras informações básicas dos artigos. O conteúdo completo não está disponível diretamente pela API.



# Kultivi
## Documentação:

Não há documentação oficial de API pública disponível até o momento.
Site oficial: https://kultivi.com/

## Requisitos:

A Kultivi não fornece uma API pública ou oficial para acesso a cursos e conteúdos de forma automatizada.
O conteúdo pode ser acessado manualmente através do site ou via canal do YouTube oficial, que contém a maior parte dos cursos.
Canal no YouTube: https://www.youtube.com/c/Kultivi
Limitações:

- Sem API pública: Não há meio oficial de integrar diretamente via requisições programáticas.
- Scraping: Qualquer tentativa de coleta automatizada precisa respeitar os termos de uso do site.
- YouTube como alternativa: Como os cursos estão disponíveis no YouTube, a melhor maneira de integrar o conteúdo é via YouTube Data API v3, filtrando pelo canal "Kultivi".
- Sem licenciamento aberto: Conteúdo gratuito para uso pessoal, mas não necessariamente liberado para redistribuição ou uso comercial em outras plataformas.

