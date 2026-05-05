# Analisador de Logs de Automacao — Trajetoria Consultoria

## Contexto

A Trajetoria opera dezenas de automacoes para seus clientes: geracao de relatorios,
importacao de notas fiscais, sincronizacao de CRM, envios de e-mail e conciliacoes
bancarias. Cada execucao gera um registro de log em CSV.

O time precisa de visibilidade sobre falhas. Hoje essa analise e feita manualmente,
o que leva horas e atrasa a identificacao de problemas criticos.

## Objetivo

Construir um agente que leia os arquivos de log da pasta `logs/`, identifique padroes
de falha e gere automaticamente um relatorio executivo para o gestor de operacoes.

## Entradas

Pasta `logs/` com arquivos `.csv`, um por mes.

Colunas de cada arquivo:

- `data_execucao` — data e hora da execucao no formato `YYYY-MM-DD HH:MM:SS`
- `nome_automacao` — nome da automacao executada
- `cliente` — cliente para o qual a automacao rodou
- `status` — `sucesso` ou `falha`
- `tipo_erro` — tipo do erro, vazio se `status = sucesso`
- `duracao_segundos` — tempo de execucao em segundos
- `impacto_horas` — horas desperdicadas estimadas em caso de falha, `0` se sucesso

## Saida esperada

Arquivo `relatorio_falhas.md` na raiz da pasta `time-ti/` com:

1. **Resumo executivo** — 3 frases descrevendo o cenario geral de falhas no periodo
2. **Visao geral do periodo** — total de execucoes, total de falhas, taxa de falha (%)
3. **Falhas por tipo de erro** — tabela ordenada por frequencia (tipo, quantidade, % do total de falhas)
4. **Top 5 automacoes mais problematicas** — tabela com nome, total de falhas, taxa de falha e impacto em horas
5. **Recomendacoes de acao** — 3 acoes prioritarias com justificativa baseada nos dados
6. **Tendencia mensal** — comparativo de taxa de falha entre janeiro, fevereiro e marco

## Restricoes

- Nao modificar os arquivos CSV originais na pasta `logs/`
- Nao usar bibliotecas alem de `pandas`, `pathlib` e a estrategia definida para Gemini
- O relatorio deve ser legivel por um gestor nao tecnico
- Numeros de impacto devem ser apresentados em horas totais, nao em segundos
- Quando o contexto da atividade pedir, dividir o trabalho em etapas revisaveis

## Etapa bonus — Resumo executivo via Gemini

Apos gerar o relatorio com os dados calculados, usar a API do Gemini para redigir o
resumo executivo de forma mais natural e orientada ao gestor.

Diretrizes:

- usar `GEMINI_API_KEY` como variavel de ambiente;
- enviar os indicadores principais como contexto no prompt;
- substituir o resumo manual pelo retorno da API;
- tratar o caso em que a chave nao esta disponivel ou a chamada falha.

## Materiais de apoio

- `tips/README.md` — instrucoes para preparar ambiente e rodar a atividade
- `challenge/README.md` — desafio adicional de exposicao do projeto via API ou serverless
