# Protocolo de Comunicação entre Agentes

Este arquivo define COMO os agentes deste cofre trabalham juntos. Todo agente deve segui-lo.

## Princípios
1. **Fonte vs multiplicador.** O dono é a fonte (pensa, decide, aprova). Os agentes multiplicam. Nenhum agente escreve notas permanentes fora de _ai/ nem age fora de _ai/ sem aprovação explícita.
2. **Handoff explícito.** Quando um agente termina sua parte, ele escreve um "handoff" e nomeia o próximo agente. Nunca encerra no vácuo.
3. **Estado compartilhado.** Todo trabalho de um projeto vive em `_ai/projects/<slug>/`. Os agentes leem e escrevem o estado ali. É assim que eles "conversam": pelo arquivo de estado, não por memória.
4. **Confirmação por etapa.** O dono pediu confirmação em cada fase (arquitetura, design, código). Nenhum agente avança de fase sem o dono dizer "aprovado".

## Arquivo de estado de projeto
Cada projeto tem `_ai/projects/<slug>/estado.md` com esta estrutura:
```
# Projeto: <nome>
## Status: <fase atual> | aguardando aprovação? <sim/não>
## Briefing: <link ou resumo>
## Fase 1 — Arquitetura: <pendente/aprovada> → ver decisao-arquitetura.md
## Fase 2 — Design: <pendente/aprovada> → ver design.md
## Fase 3 — Código: <pendente/aprovada>
## Fase 4 — Auditoria: <pendente/aprovada> → ver auditoria.md
## Handoff atual: <agente da vez> — <o que ele deve fazer>
## Pendências/Riscos:
## Log de decisões: (links para _ai/decisions/)
```

## Formato de handoff (todo agente termina assim)
```
--- HANDOFF ---
De: <agente>
Fase concluída: <qual>
Resultado: <1-2 linhas>
Aguardando do dono: <o que preciso aprovar/responder>
Próximo agente: <nome> (só inicia após aprovação do dono)
```

## Vocabulário de comando do dono
- "aprovado" / "pode seguir" → agente da vez avança e faz handoff pro próximo.
- "ajusta X" → agente da vez revisa sem trocar de fase.
- "volta pra fase Y" → reabre fase anterior.
