# Upgrade do pipeline /novosite — Blueprint primeiro

**Data:** 2026-06-15

## Motivação
Trocar o fluxo "fase a fase com aprovação a cada passo" por "blueprint completo aprovado uma vez". Sites multipágina por padrão (landing só se pedido), espaçamento generoso, decisão de mídia hero explícita.

## Arquivos sobrescritos
- `_ai/agents/PIPELINE-novosite.md` — agora 4 etapas (Briefing → Blueprint → Execução → Auditoria). Aprovação única no blueprint. Inclui ETAPA 2.1 de decisão de stack (HTML puro / Astro / fullstack).
- `_ai/agents/arquiteto-frontend.md` — decisão FRONTEND vs FULLSTACK explícita por sinais (login/painel/dados → fullstack). Multipágina por padrão. Saída entra no blueprint, não em fase separada de "decisao-arquitetura".
- `_ai/agents/designer-ui.md` — RESPIRO GENEROSO (padding vertical 6-8rem, combate ao compacto). Mídia hero (vídeo vs imagem) decidida com justificativa, sem "cara de IA genérica". Saída integrada ao blueprint.

## Arquivos criados
- `_ai/skills/blueprint-site.md` — novo documento-mestre de planejamento (mapa de páginas, seções, fluxos de clique, design, mídia, stack, backend, conteúdo). Inclui referências de estrutura BR (Locatelli, Patrus/Bautz, Itaipu/Ryazbek) — só padrão de organização, nunca conteúdo.
- `_ai/skills/novo-app-fullstack.md` — Next + backend + Postgres/Supabase + Zod + Auth, multipágina, com checklist e anti-padrões.

## Mudanças de comportamento
1. Pergunta tudo de uma vez no briefing.
2. Devolve UM blueprint completo (em `_ai/projects/<slug>/blueprint.md`) e PARA.
3. Após "aprovado", codifica o site INTEIRO em `C:\Projetos\<slug>` (com aprovação para escrever fora de _ai/).
4. Auditoria fecha a entrega.

## Itens não tocados
Nenhum site em produção foi modificado. Mudança contida em `_ai/`.
