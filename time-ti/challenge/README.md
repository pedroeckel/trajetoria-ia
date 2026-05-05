# Challenge — Integracao com Ambiente Interno

## Nova solicitacao da equipe

O time interno da Trajetoria avaliou o prototipo atual e quer dar o proximo passo: integrar o gerador de relatorios ao ambiente operacional da empresa.

Hoje o projeto gera o arquivo `relatorio_falhas.md` localmente. A nova necessidade e disponibilizar esse resultado de forma acessivel para outros sistemas internos, permitindo que o relatorio seja acionado sob demanda e consumido sem depender de execucao manual no terminal.

## Contexto da demanda

A equipe de operacoes quer conseguir:

- disparar a geracao do relatorio por requisicao;
- consultar o resultado mais recente de forma padronizada;
- facilitar a integracao futura com o portal interno da empresa.

Para isso, a equipe pediu uma evolucao do projeto com foco em exposicao via API e preparacao para deploy.

## Desafio

Voce deve propor e implementar uma forma de expor o projeto no ambiente interno da empresa usando uma das abordagens abaixo:

### Opcao 1 — API com FastAPI

Transformar o projeto em uma API HTTP usando `FastAPI`, com endpoints para:

- disparar a geracao do relatorio;
- retornar o conteudo do relatorio gerado;
- opcionalmente retornar os principais indicadores em JSON.

### Opcao 2 — Abordagem serverless

Adaptar o projeto para uma abordagem serverless, usando um framework ou plataforma de deploy que permita expor a execucao por HTTP.

Exemplos de direcao:

- funcao HTTP;
- endpoint serverless;
- deploy simples em plataforma compatível com Python.

## Requisitos da equipe

Independentemente da abordagem escolhida, a entrega deve:

- reaproveitar ao maximo o codigo atual;
- evitar duplicacao da regra de negocio;
- manter a leitura automatica do `.env`;
- continuar usando o controle de dependencias com `Poetry`;
- manter fallback seguro quando o Gemini falhar;
- permitir execucao local para testes antes do deploy.

## O que deve ser pensado

O time quer que a solucao seja preparada com mentalidade de software real. Portanto, considere:

- separacao entre camada HTTP e regra de negocio;
- contrato claro de entrada e saida;
- tratamento de erros;
- organizacao minima para manutencao;
- instrucoes claras de execucao local;
- estrategia simples de deploy.

## Entregaveis esperados

Ao finalizar esse challenge, espera-se que voce entregue:

1. uma proposta de arquitetura curta explicando a abordagem escolhida;
2. a implementacao da API ou da funcao serverless;
3. instrucoes para rodar localmente;
4. instrucoes para fazer deploy;
5. exemplos de chamada para uso interno da empresa.

## Criterios de avaliacao

Os pontos observados pela equipe serao:

- clareza da solucao;
- reaproveitamento do codigo existente;
- simplicidade de operacao;
- qualidade da organizacao tecnica;
- facilidade de integracao com o ambiente interno.

## Dica

Se escolher FastAPI, pense em como transformar o fluxo atual em funcoes reutilizaveis, em vez de deixar toda a regra presa ao `main.py`.

Se escolher serverless, pense em como reduzir dependencias de ambiente e simplificar o ponto de entrada da aplicacao.
