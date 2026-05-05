# Briefing do Projeto X — Trajetória Consultoria
**Documento de referência para o exercício do Módulo 05**

---

## Contexto do Cliente

**Cliente:** Distribuidora Sul Ltda.
**Setor:** Distribuição e logística de alimentos
**Porte:** 280 funcionários, 12 centros de distribuição no Sul do Brasil
**Contato principal:** Rodrigo Faria — Diretor de Operações

---

## O Problema que Originou o Projeto

A Distribuidora Sul enfrentava um gargalo crítico na operação: os relatórios operacionais
e financeiros eram gerados manualmente por uma equipe de 4 analistas, levando entre
2 e 3 dias úteis para ficarem prontos. Nesse intervalo, a diretoria tomava decisões
baseadas em dados desatualizados.

Além disso, a conciliação bancária e o controle de inadimplência eram feitos em
planilhas Excel sem automação, gerando erros frequentes e retrabalho.

**Frase do cliente na reunião de kick-off:**
> "Hoje eu descubro que um cliente está inadimplente quando o vendedor liga reclamando
> que o pedido foi bloqueado. Preciso saber isso antes — não depois."

---

## Objetivos do Projeto

1. **Automatizar** a geração de relatórios operacionais diários (eliminando os 2–3 dias de espera)
2. **Implementar** alertas automáticos de inadimplência com 5 dias de antecedência
3. **Criar** um dashboard executivo atualizado em tempo real para a diretoria
4. **Integrar** os sistemas de ERP (Totvs) e CRM (Salesforce) para eliminar retrabalho de digitação

---

## Escopo Contratado

| Item | Incluído | Observação |
|---|---|---|
| Agente de geração de relatórios | ✅ | Diário, automático |
| Alertas de inadimplência | ✅ | E-mail + WhatsApp |
| Dashboard executivo | ✅ | Acesso via navegador |
| Integração Totvs (ERP) | ✅ | Fase 2 — em andamento |
| Integração Salesforce (CRM) | ✅ | Fase 2 — em andamento |
| Treinamento do time | ✅ | Fase 3 — pendente |
| Suporte pós-go-live | ✅ | 3 meses inclusos |
| Desenvolvimento de app mobile | ❌ | Fora do escopo |
| Migração de dados históricos (+5 anos) | ❌ | Negociação separada |

---

## Cronograma e Fases

| Fase | Descrição | Prazo | Status |
|---|---|---|---|
| Fase 1 — Diagnóstico | Mapeamento de processos e arquitetura-alvo | 30/01/2026 | ✅ Concluído |
| Fase 2 — Implementação | Desenvolvimento dos agentes e integrações | 31/03/2026 | 🟡 Em andamento |
| Fase 3 — Estabilização | Treinamento, go-live e monitoramento | 20/05/2026 | ⏳ Pendente |

---

## Budget do Projeto

| Item | Valor contratado |
|---|---|
| Valor total do contrato | R$ 85.000 |
| Horas contratadas (total) | 272 horas |
| Taxa horária média | R$ 312,50/hora |
| Budget consumido até março | R$ 64.250 (75,6%) |
| Budget restante | R$ 20.750 (24,4%) |
| Horas contratadas restantes | ~72 horas |

---

## Situação Atual (março 2026)

### O que está funcionando bem
- Fase de diagnóstico entregue dentro do prazo e aprovada pela diretoria
- Agente de relatórios em estágio avançado (80% concluído)
- Boa relação com o time técnico do cliente

### Pontos de atenção
- Integração com o ERP (Totvs) está atrasada — dependência de credenciais de acesso
  que o cliente ainda não forneceu
- Taxa de entrega no prazo ficou em 72% (meta: 85%) — impactada pelo atraso da integração
- Adoção pelo time do cliente está baixa (55%) — usuários treinados não estão usando o dashboard
- Taxa de falha em produção acima da meta (13% vs meta de 5%) — sendo investigada

### Riscos identificados
- **Alto:** Se as credenciais do ERP não chegarem até 31/03, a Fase 2 não será entregue no prazo
- **Médio:** Baixa adoção pode comprometer a percepção de valor pelo cliente no go-live
- **Baixo:** Budget consumido está dentro do esperado, mas horas extras não estão previstas

---

## Próxima Reunião com o Cliente

**Data:** 01/04/2026
**Formato:** Presencial — sede da Distribuidora Sul em Porto Alegre
**Participantes:** Rodrigo Faria (Dir. Operações), Fernanda Costa (TI), time Trajetória
**Pauta proposta:**
1. Status das integrações (bloqueio das credenciais)
2. Plano de ação para a adoção
3. Revisão do cronograma da Fase 3

---

## Instruções para o Exercício

### Como usar este documento no Claude

1. Crie um novo Projeto no Codex usando a pasta do time-negocio
2. Cole o seguinte texto no campo de instruções do Project:

```
Você é um assistente de análise de projetos da Trajetória Consultoria.
Seu papel é apoiar o gestor de projetos na análise de indicadores,
identificação de riscos e geração de relatórios executivos.

Público: diretores e gerentes sem perfil técnico.
Tom: profissional, direto, orientado a decisão.
Idioma: português brasileiro.
Formato padrão: resumo executivo → dados → análise → recomendações.
```

3. Verifique se este arquivo (`briefing_cliente.md`) e a planilha (`dados_projeto_x.xlsx`) estão presentes no projeto

### Perguntas sugeridas para explorar

**Análise geral:**
> "Com base no briefing e na planilha, qual é o status real deste projeto?
>  Estamos no prazo e dentro do orçamento?"

**Aprofundamento:**
> "Quais são os 3 maiores riscos que podem impedir a entrega no prazo?
>  O que poderia ser feito em cada caso?"

> "A taxa de adoção de 55% preocupa. O que pode estar causando isso e
>  quais ações o time deveria tomar antes do go-live?"
>

**Geração do relatório:**
Adicione as skills de documentos (word) e apresentações (powerpoint)

**Geração do relatório:**
> "Gera um relatório executivo de uma página para apresentar ao cliente
>  na reunião de 01/04. Inclui: status geral com semáforo, resumo em
>  3 frases, tabela de KPIs, análise dos desvios e plano de ação com
>  responsáveis e prazos."

**Transformar em apresentação:**
> "Transforma este relatório em um roteiro de 5 slides. Para cada slide:
>  título, pontos principais e o que falar (notas do apresentador)."

---

*Gestão Quanti | Pedro Eckel — pedroeckel@gmail.com*
