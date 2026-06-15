# Pipeline: /novosite
> Executado pelo [[orquestrador]]. Cria um site profissional com confirmação em cada fase. Segue o [[PROTOCOLO]].

## FASE 0 — Briefing
Se o dono não deu detalhes, chamar [[briefing-cliente]] para coletar: nome do negócio, ramo, objetivo do site (vender/institucional/captar lead), público, referências visuais, precisa de SEO?, precisa de área logada/sistema?, orçamento/prazo, domínio/hospedagem.
Criar slug e a pasta `_ai/projects/<slug>/` com `estado.md` e `briefing.md`.

## FASE 1 — Arquitetura (chamar [[arquiteto-frontend]])
Decide: tipo (institucional / conteúdo / app), stack (do [[Arsenal-Web-Dev]] e do [[stack-padrao]]), estrutura de pastas, integrações (form, pagamento, CMS).
Grava `_ai/projects/<slug>/decisao-arquitetura.md` e registra ADR em `_ai/decisions/`.
**PAUSA → dono aprova.**

## FASE 2 — Design (chamar [[designer-ui]])
Define: tom visual, paleta (com hex), escala tipográfica, grid, tokens CSS (custom properties), referência de componentes. Gera `design.md` com os tokens prontos pra copiar.
**PAUSA → dono aprova.**

## FASE 3 — Implementação
Seguir a skill certa: institucional → [[novo-site-institucional]]; app → [[novo-app-next]]; conteúdo → landing-astro.
Codar respeitando arquitetura + tokens do design. Código vai pra pasta do projeto (fora de _ai/ → pedir aprovação pra escrever fora).
**PAUSA → dono aprova.**

## FASE 4 — Auditoria (chamar [[auditor-performance]])
Roda checklist de perf/SEO/acessibilidade, gera `auditoria.md` em `_ai/outputs/`. Corrige o crítico. Entrega final + instruções de deploy.

## Regra de ouro
Uma fase por vez. Sempre fazer handoff e esperar "aprovado".
