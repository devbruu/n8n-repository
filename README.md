# Assistente de Investimentos com RPA e n8n

Projeto do desafio da DIO. Montei no n8n um fluxo que recebe dados de clientes, cruza o perfil de investidor com uma tabela de investimentos (CSV) e gera uma mensagem de recomendação para cada cliente.

## O que eu fiz

- Webhook (POST) para receber os dados dos clientes
- HTTP Request para buscar o CSV de investimentos
- Nós Code em JavaScript para transformar o CSV em lista, escolher o produto de acordo com o perfil e o saldo, e montar 3 mensagens por cliente (uma é sorteada)
- Respond to Webhook para devolver o resultado

Fiz o MVP, com mensagens estáticas por perfil. Os testes foram com dados fictícios, usando o n8n local e `curl.exe` no PowerShell.

## O que ficou de fora

A parte com IA (Gemini) e o envio por Gmail. Tentei configurar, mas esbarrei em erros de credencial e nas limitações do app do Google em modo de teste, e não consegui terminar a tempo.

## Dificuldades

Os maiores erros foram do webhook (404 em modo de teste e a configuração do Respond to Webhook) e das credenciais do Google. Usei IA como apoio para entender os erros e o código.

## Arquivos

- `n8n/workflow.json`: o fluxo exportado
- `clientes.json`: 10 clientes fictícios
- print do fluxo executado
