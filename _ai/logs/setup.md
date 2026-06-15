# Setup do segundo cérebro

**Data:** 2026-06-15

## Passo 1 — Pastas na raiz
Status: OK (já existiam da execução anterior, verificadas agora).
- 00_Inbox
- 01_Processamento
- 02_Topicos_Links
- Projetos
- Areas
- Recursos
- Arquivos
- Notas_Diarias
- Banco_Imagens
- _ai

Observação: existe `Bem-vindo.md` na raiz, pré-existente, não foi tocado.

## Passo 2 — Subpastas dentro de _ai
Status: OK (já existiam, verificadas agora).
- outputs
- skills
- logs
- projects
- agents
- templates
- decisions
- briefings

## Passo 3 — CLAUDE.md na raiz
Status: OK (conteúdo verificado, bate com o solicitado).

## Passo 4 — Recursos/Arsenal-Web-Dev.md
Status: OK. Arquivo criado em 2026-06-15 com o catálogo de ferramentas web dev (14 seções + stacks recomendadas).

## Passo 5 — Arquivos de skill em _ai/skills/
Status: AGUARDANDO conteúdo do usuário (vem depois do Arsenal).

## Passo extra (Parte 1 de 3) — READMEs das subpastas de _ai/
Status: OK. Criados em 2026-06-15:
- _ai/agents/README.md
- _ai/skills/README.md
- _ai/outputs/README.md
- _ai/logs/README.md
- _ai/projects/README.md
- _ai/templates/README.md
- _ai/decisions/README.md
- _ai/briefings/README.md

## Parte 2 de 3 — Agentes em _ai/agents/
Status: OK (concluído). Criados em 2026-06-15:
- _ai/agents/INDEX.md
- _ai/agents/orquestrador.md
- _ai/agents/arquiteto-frontend.md
- _ai/agents/revisor-codigo.md
- _ai/agents/auditor-performance.md
- _ai/agents/designer-ui.md
- _ai/agents/bibliotecario.md

## Parte 3 de 3 — Agentes restantes + briefings
Status: OK (concluído). Criados em 2026-06-15:

Agentes (negócio + acadêmico):
- _ai/agents/proposta-comercial.md
- _ai/agents/prospector-clientes.md
- _ai/agents/gestor-projeto.md
- _ai/agents/tutor-algoritmos.md
- _ai/agents/revisor-academico.md

Briefings base:
- _ai/briefings/stack-padrao.md
- _ai/briefings/clientes.md
- _ai/briefings/preferencias.md

## Resumo geral
- READMEs das 8 subpastas de _ai/: CONCLUÍDO
- Agentes (11 do INDEX, todos com .md): CONCLUÍDO
- Briefings base (3): CONCLUÍDO
- Pendente: skills em _ai/skills/ (Passo 5 original — aguardando conteúdo do usuário).

## Bloco 1 de 4 — Protocolo + orquestrador v2
Status: OK. Atualizado em 2026-06-15.
- _ai/agents/PROTOCOLO.md (novo) — princípios, formato de estado.md, handoff e vocabulário de comando.
- _ai/agents/orquestrador.md (sobrescrito) — agora é o maestro com comando /novosite e roteamento explícito.

## Bloco 2 de 4 — Pipeline + agentes técnicos v2
Status: OK. Atualizado em 2026-06-15.
- _ai/agents/PIPELINE-novosite.md (novo) — 4 fases com pausas de aprovação.
- _ai/agents/arquiteto-frontend.md (sobrescrito) — fase 1 do pipeline.
- _ai/agents/designer-ui.md (sobrescrito) — fase 2 do pipeline.
- _ai/agents/auditor-performance.md (sobrescrito) — fase 4 do pipeline.

## Bloco 3 de 4 — Briefing + agentes restantes v2
Status: OK. Atualizado em 2026-06-15.
- _ai/agents/briefing-cliente.md (novo) — FASE 0 do pipeline, coleta com 9 perguntas.
- _ai/agents/revisor-codigo.md (sobrescrito) — checklist expandido + severidade visual.
- _ai/agents/proposta-comercial.md (sobrescrito) — escopo em fases + 3 níveis (Essencial/Completo/Premium).
- _ai/agents/prospector-clientes.md (sobrescrito) — critérios e sinais de oportunidade explícitos.
- _ai/agents/gestor-projeto.md (sobrescrito) — acoplado ao estado.md do projeto.
- _ai/agents/tutor-algoritmos.md (sobrescrito) — método socrático reforçado.
- _ai/agents/revisor-academico.md (sobrescrito) — modo "corrija direto" preservado.
- _ai/agents/bibliotecario.md (sobrescrito) — agora cuida dos INDEX e da rotina de manutenção.

Referências citadas que ainda não existem (a criar no Bloco 4):
- _ai/skills/auditar-performance.md
- _ai/skills/novo-site-institucional.md
- _ai/skills/novo-app-next.md

## Bloco 4 de 4 — Fechamento: INDEX + grafo + CLAUDE.md reforçado
Status: OK. Atualizado em 2026-06-15.

Tarefa 1 — INDEX.md sobrescrito:
- _ai/agents/INDEX.md agora explica o fluxo, lista por categoria com wikilinks, e mostra os comandos rápidos.

Tarefa 2 — Rodapé `Ver: [[INDEX]] · [[PROTOCOLO]]` adicionado aos 12 agentes:
- orquestrador, briefing-cliente, arquiteto-frontend, designer-ui, auditor-performance, revisor-codigo, proposta-comercial, prospector-clientes, gestor-projeto, tutor-algoritmos, revisor-academico, bibliotecario.
- Não adicionado a INDEX.md, PROTOCOLO.md, PIPELINE-novosite.md e README.md (meta-files, não agentes — link a si mesmo seria ruído).

Tarefa 3 — CLAUDE.md (raiz) sobrescrito:
- Versão reforçada: rota via orquestrador, comando /novosite, regra de fronteira, confirmação por fase, registro em logs.

## Pendências remanescentes
- Skills em _ai/skills/ (referenciadas por PIPELINE e auditor-performance):
  - auditar-performance
  - novo-site-institucional
  - novo-app-next
  - landing-astro
- Estes ainda dependem do conteúdo a ser fornecido pelo dono.

## Doc de expansão adicionada
Status: OK. 2026-06-15.
- Recursos/Expansao-Mega-Cerebro.md — roadmap de 8 camadas (MCPs, plugins, comandos, dashboards, automação, memória semântica, conteúdo, governança) com ordem de implementação semanal sugerida.
- Autorização para escrever fora de _ai/: explícita no próprio cabeçalho do documento ("Coloque em `Recursos/`").

## Índice de skills criado
Status: OK. 2026-06-15.
- _ai/skills/INDEX.md — lista mestra com 25 skills em 5 categorias (Web Dev, Negócio, Acadêmico, Organização, Conteúdo).
- Conteúdo individual de cada skill: AGUARDANDO blocos de instalação do dono.

## Bloco A de 4 — Skills web dev (scaffolding)
Status: OK. 2026-06-15.
- _ai/skills/novo-site-institucional.md — HTML/CSS/JS + GSAP + Lucide.
- _ai/skills/novo-app-next.md — Next.js 16 + TS + shadcn + Tailwind v4.
- _ai/skills/landing-astro.md — Astro + Tailwind + Motion.

## Bloco C de 4 — Skills de negócio + acadêmico
Status: OK. 2026-06-15.
Negócio:
- _ai/skills/proposta-cliente.md
- _ai/skills/prospectar-leads.md
- _ai/skills/mensagem-cliente.md
- _ai/skills/escopo-projeto.md
- _ai/skills/status-semanal.md
Acadêmico:
- _ai/skills/trilha-estudo.md
- _ai/skills/explicar-algoritmo.md
- _ai/skills/revisar-texto-academico.md

Observação: Bloco B (web dev — auditar-performance, componente-animado, design-tokens, seo-onpage, deploy-checklist, revisar-codigo, responsivo-fix) ainda não foi colado pelo dono. Bloco D (organização + conteúdo + skill acadêmica resumo-aula) também pendente.

## Skill profissional 1 de 2 — novo-site-institucional v2
Status: OK. 2026-06-15.
- _ai/skills/novo-site-institucional.md sobrescrito com versão profissional: objetivo, padrão de qualidade (Awwwards), estrutura, exemplos de tokens/hero/scroll, anti-padrões, checklist de entrega.

## Skills profissionais 2 de 2 — design-tokens, novo-app-next, proposta-cliente
Status: OK. 2026-06-15.
- _ai/skills/design-tokens.md (NOVO — não existia ainda, mesmo estando no INDEX) — método de decisão, exemplo de design.md, anti-padrões, critério de sucesso.
- _ai/skills/novo-app-next.md (sobrescrito) — stack justificada, exemplo Zod compartilhado, anti-padrões, checklist.
- _ai/skills/proposta-cliente.md (sobrescrito) — 7 seções de estrutura, ancoragem em 3 níveis, critério de sucesso explícito + loop de feedback.

## Preencher pastas vazias — item 3 resolvido
Status: OK. 2026-06-15.
Templates (4):
- _ai/templates/projeto.md — estado.md de projeto.
- _ai/templates/proposta.md — proposta comercial.
- _ai/templates/decisao.md — ADR.
- _ai/templates/mensagem-cliente.md — abordagem + follow-up.
Decisão inicial:
- _ai/decisions/2026-06-15-arquitetura-segundo-cerebro.md — registra a escolha do C:\Cofre + autonomia só em _ai/ + Git como rede.
Projeto exemplo:
- _ai/projects/EXEMPLO-clinica/estado.md — mostra o formato preenchido (descartável).
Briefing:
- _ai/briefings/glossario.md — vocabulário do sistema.
