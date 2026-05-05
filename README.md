# Módulo 05 — Hands-on: Construindo um Agente do Zero
**Curso: Agentes de IA na Prática | Gestão Quanti × Trajetória Consultoria**

---

## Estrutura do Exercício

```
modulo-05-handson/
├── README.md               ← este arquivo
├── time-ti/
│   ├── AGENTS.md           ← contexto para o Codex (leia antes de começar)
│   └── logs/
│       ├── automacoes_jan.csv
│       ├── automacoes_fev.csv
│       └── automacoes_mar.csv
└── time-negocio/
    ├── briefing_cliente.md ← contexto do projeto para o Claude
    └── dados_projeto_x.xlsx ← planilha com indicadores do projeto
```

---

## Tempo total: 45 minutos

| Fase | Duração | Quem |
|---|---|---|
| Briefing conjunto | 5 min | Todos |
| Prática paralela | 30 min | Grupos separados |
| Demo e troca | 10 min | Todos |

---

## Time de TI — O que fazer

**Ferramenta:** Codex (app desktop)

1. Abra o Codex e conecte esta pasta (`time-ti/`) como pasta do projeto
2. Leia o `AGENTS.md` — ele define o objetivo, entradas e saída esperada
3. Peça ao agente um **plano** antes de qualquer implementação
4. Revise o plano com o grupo e autorize
5. Acompanhe a implementação — commite cada etapa
6. Valide o resultado contra o `AGENTS.md`

**Entregável:** arquivo `relatorio_falhas.md` gerado automaticamente pelo agente

---

## Time de Negócios — O que fazer

**Ferramenta:** Claude.ai (Projects) ou Cowork

1. Crie um novo Project no Claude.ai
2. Configure o contexto do Project (instruções estão no `briefing_cliente.md`)
3. Faça upload dos dois arquivos da pasta `time-negocio/`
4. Faça as perguntas de análise sugeridas no `briefing_cliente.md`
5. Peça ao Claude para gerar o relatório executivo
6. Transforme em roteiro de apresentação

**Entregável:** relatório executivo de status do projeto gerado pelo Claude

---

## Resultado esperado da demo (10 min finais)

Cada grupo apresenta em **5 minutos**:
- O que o agente produziu
- Uma coisa que surpreendeu (positivo ou negativo)
- Como isso se conectaria ao trabalho real na Trajetória

**Pergunta de encerramento para o grupo:**
> Como o agente do time de TI e o agente do time de negócios poderiam trabalhar juntos em um projeto real da Trajetória?

---

*Pedro Eckel | pedroeckel@gmail.com | Gestão Quanti*
