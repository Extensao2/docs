#  MVP: Coleta e Análise Educacional

## Resultado Esperado do MVP

Um sistema funcional e validável que simula o comportamento do usuário, registra eventos com estrutura padronizada, processa os dados automaticamente e exibe insights iniciais de engajamento para validação e evolução futura.

## Entregáveis Principais

- Sistema de rastreamento via Postman simulando interações reais do usuário.
- API de coleta operando no n8n, com validação e persistência dos dados em MongoDB.
- Processamento automatizado dos eventos para geração de insights de engajamento.
- Exibição clara dos resultados por meio de logs
- Documentação de todo o fluxo

## Stacks Utilizada

| Componente        | Tecnologia       |
|-------------------|------------------|
| Orquestração      | `n8n`            |
| Banco de Dados    | `MongoDB`        |
| Frontend Simulado |  `Postman`       |
| Backend/API       | `n8n Webhooks`   |
| IA                | `n8n + Code Node`|
| Hospedagem        | `Docker (local)` |
