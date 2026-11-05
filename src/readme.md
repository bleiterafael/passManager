# Sobre o projeto

Este projeto consiste na criação de uma API para gerar e gerenciar senhas fortes.

## Diretrizes do projeto

- A aplicação compila sem erros ou warnings
- Todos os testes passam
- A aplicação roda sem erros

## Sobre a API

A ideia deste projeto é criar uma API simples, com dois endpoints, sendo um que gera senhas fortes seguindo um padrão e outro que dado um GUID, permite consultar uma senha associada.

As senhas tem que ter caracteres especiais, pelo menos 16 caracteres e não podem incluir espaços em branco.

Toda senha gerada é armazenada no banco e retorna um GUID para ser encontrada posteriormente.

Não há necessidade de encriptar senha ou outros recursos de segurança no momento.

### Stack

- .NET 10, C#, Minimal API
- Persistência em SQLite com EF Core
- Testes com xUnit

### Arquitetura

- Endpoint não acessa banco diretamente, sempre via serviço de aplicação
- Regra de negócio não vive no endpoint nem no handler HTTP

### Testes e Qualidade

- Toda regra de negócio precisa ter teste unitário
- Todo endpoint precisa ter ao menos um teste de integração de caminho feliz
- Erro de validação sempre retorna 400 com ProblemDetails
