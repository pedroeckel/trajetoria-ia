# Analisador de Logs de Automação — Trajetória Consultoria

## Contexto
A Trajetória opera dezenas de automações para seus clientes: geração de relatórios,
importação de notas fiscais, sincronização de CRM, envios de e-mail e conciliações
bancárias. Cada execução gera um registro de log em CSV.

O time precisa de visibilidade sobre falhas — hoje essa análise é feita manualmente,
o que leva horas e atrasa a identificação de problemas críticos.

## Objetivo
Construir um agente que leia os arquivos de log da pasta `/logs`, identifique padrões
de falha e gere automaticamente um relatório executivo para o gestor de operações.

## Entradas
Pasta `logs/` com arquivos `.csv` — um por mês.

Colunas de cada arquivo:
- `data_execucao` — data e hora da execução (formato: YYYY-MM-DD HH:MM:SS)
- `nome_automacao` — nome da automação executada
- `cliente` — cliente para o qual a automação rodou
- `status` — "sucesso" ou "falha"
- `tipo_erro` — tipo do erro (vazio se status = sucesso)
- `duracao_segundos` — tempo de execução em segundos
- `impacto_horas` — horas desperdiçadas estimadas em caso de falha (0 se sucesso)

## Saída esperada
Arquivo `relatorio_falhas.md` na raiz da pasta `time-ti/` com:

1. **Resumo executivo** — 3 frases descrevendo o cenário geral de falhas no período
2. **Visão geral do período** — total de execuções, total de falhas, taxa de falha (%)
3. **Falhas por tipo de erro** — tabela ordenada por frequência (tipo, quantidade, % do total de falhas)
4. **Top 5 automações mais problemáticas** — tabela com nome, total de falhas, taxa de falha e impacto em horas
5. **Recomendações de ação** — 3 ações prioritárias com justificativa baseada nos dados
6. **Tendência mensal** — comparativo de taxa de falha entre janeiro, fevereiro e março

## Restrições
- NÃO modificar os arquivos CSV originais na pasta `logs/`
- NÃO usar bibliotecas além de `pandas`, `pathlib` e `google-generativeai` (já disponíveis)
- O relatório deve ser legível por um gestor não técnico — evitar jargões de código
- Números de impacto devem ser apresentados em horas totais, não em segundos
- Commitar cada etapa separadamente: leitura → análise → geração do relatório → integração Gemini

## Etapa Bônus — Resumo Executivo via API do Gemini
Após gerar o relatório com os dados calculados, use a API do Gemini para redigir o
resumo executivo (seção 1) de forma mais natural e orientada ao gestor.

- A chave de API está disponível na variável de ambiente `GEMINI_API_KEY`
- Use o modelo `gemini-1.5-flash`
- Envie os indicadores principais como contexto no prompt
- Substitua o resumo gerado manualmente pelo retorno da API
- Trate o caso em que a chave não está disponível (fallback para texto fixo)

## Como começar
Antes de escrever qualquer código, apresente um plano detalhado com:
- Quais arquivos serão criados
- Estrutura do código (funções principais)
- Como cada seção do relatório será calculada
- Como a chamada à API do Gemini será integrada

Aguarde aprovação do plano antes de implementar.
