# 2026-06-16 — Upgrade do /novosite para nível sênior

## Objetivo
Transformar o pipeline `/novosite` num fluxo de nível sênior: entrada multimodal, pesquisa autônoma, agentes críticos, decisão de backend, mídia integrada, design intelligence via ui-ux-pro-max, troubleshooting. Tudo dentro de `/_ai/`.

## Arquivos criados / modificados

### Criados
- `_ai/agents/analista-entrada.md` — primeiro contato, processa material bruto do cliente.
- `_ai/agents/pesquisador.md` — pesquisa negócio e mercado antes do blueprint.
- `_ai/agents/PROTOCOLO-CRITICA.md` — postura crítica obrigatória dos agentes.
- `_ai/agents/estrategista.md` — define mensagem nº1, CTA, jornada e provas.
- `_ai/agents/arquiteto-backend.md` — decide front vs fullstack + o que sempre falta.
- `_ai/skills/midia-hero.md` — decisão vídeo/imagem + boas práticas + anti-padrões.
- `_ai/skills/design-intelligence.md` — conexão com ui-ux-pro-max (PARTE B; instalação PARTE A pendente).
- `_ai/briefings/troubleshooting.md` — problemas comuns e soluções.

### Modificados
- `_ai/agents/PIPELINE-novosite.md` — sobrescrito com pipeline sênior de 7 etapas.
- `_ai/agents/arquiteto-frontend.md` — adicionada linha do PROTOCOLO-CRITICA no topo.
- `_ai/agents/designer-ui.md` — adicionada linha do PROTOCOLO-CRITICA no topo.
- `_ai/agents/revisor-codigo.md` — adicionada linha do PROTOCOLO-CRITICA no topo.
- `_ai/agents/auditor-performance.md` — adicionada linha do PROTOCOLO-CRITICA no topo.
- `_ai/agents/proposta-comercial.md` — adicionada linha do PROTOCOLO-CRITICA no topo.

## Pendência (fora do escopo /_ai/)
- **PARTE A do ARQUIVO 6:** instalar a skill externa `ui-ux-pro-max` via `/plugin marketplace add nextlevelbuilder/ui-ux-pro-max-skill` ou `git clone`. Ação manual do dono (mexe fora do cofre).

## Iteração 2 — Integração real do ui-ux-pro-max (mesmo dia)
Após inspeção do repo público `nextlevelbuilder/ui-ux-pro-max-skill` (só leitura via `gh api`, sem clonar/instalar), descobri que é um plugin do Claude Code com **7 sub-skills** (ui-ux-pro-max, design-system, design, brand, ui-styling, banner-design, slides), 326 arquivos, scripts Python e CJS.

Decisão: **não fazer mirror dentro de /_ai/** (duplicação + scripts quebrariam). Em vez disso, atualizar os 3 arquivos do cofre pra refletir o plugin real:

- `_ai/skills/design-intelligence.md` — sobrescrito com lista real das 7 sub-skills, tabela de prioridades 1→10 do SKILL.md oficial, 3 métodos de instalação, fallback se não instalado.
- `_ai/agents/designer-ui.md` — adicionada seção "Uso do plugin ui-ux-pro-max" com mapa tarefa → sub-skill e regra "identidade do cliente > sugestão genérica".
- `_ai/briefings/troubleshooting.md` — entrada do ui-ux-pro-max ampliada com 3 métodos de instalação, pré-requisitos (Python 3.x + Node), lista das 7 sub-skills e link oficial https://uupm.cc.

Nada foi executado. O dono instala quando quiser.

## Próximo passo
Atualizar `_ai/agents/INDEX.md` e `_ai/skills/INDEX.md` para incluir os novos agentes/skills, se ainda não estiverem indexados.
