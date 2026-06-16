# Troubleshooting — Problemas comuns e como resolver
> Consulta rápida quando algo der errado. Ver [[INDEX]].

## Claude Code escreveu fora de _ai/ sem permissão
→ Reverter com Git: `git checkout -- <arquivo>` ou `git restore <arquivo>`. Reforçar no CLAUDE.md a regra de fronteira. (Por isso Git é obrigatório.)

## A IA não acessa a internet (pesquisa/fetch falha)
→ Claude Code no terminal não navega por padrão. Soluções grátis: instalar um MCP de fetch/browser, OU eu colo o conteúdo da URL manualmente, OU peço a pesquisa aqui no chat e levo o resultado.

## ui-ux-pro-max não ativa / não responde
→ Conferir se instalou. Três formas válidas:
  1. Plugin: `/plugin marketplace add nextlevelbuilder/ui-ux-pro-max-skill` → `/plugin install ui-ux-pro-max@ui-ux-pro-max-skill` → confirmar com `/plugin list`.
  2. CLI npm: `npx uipro-cli init --ai claude`.
  3. Manual: `git clone https://github.com/nextlevelbuilder/ui-ux-pro-max-skill.git` e seguir README do repo.
→ Pré-requisitos: **Python 3.x** (scripts de busca) e Node (scripts CJS). Sem eles, parte das funções não roda.
→ As 7 sub-skills disponíveis são: `ui-ux-pro-max`, `design-system`, `design`, `brand`, `ui-styling`, `banner-design`, `slides`. Se uma falhar, tentar outra pelo mapa em [[design-intelligence]].
→ Home oficial: https://uupm.cc. Sem o plugin, o [[designer-ui]] funciona em modo fallback (sem bloquear o pipeline).

## Vídeo do hero trava / não dá autoplay no celular
→ Faltou `muted` + `playsinline`. Vídeo pesado: comprimir (<3MB) e usar poster. Em mobile, trocar vídeo por imagem via media query.

## Dashboards Dataview aparecem como texto
→ Plugin Dataview não está ativo. Instalar e ativar. Conferir frontmatter nas notas (status/fase/etc.).

## Graph do Obsidian todo solto
→ Faltam wikilinks nos arquivos. Rodar: "adicione no rodapé de cada agente/skill a linha Ver: [[INDEX]] · [[PROTOCOLO]]". Pastas vazias ficam soltas até serem usadas — normal.

## Arquivos com linhas embaralhadas
→ Pedir: "verifique os .md de _ai/agents e _ai/skills e liste os com linhas fora de ordem". Depois mandar corrigir os apontados.

## Site ficou "cara de template / de IA"
→ Faltou identidade real do cliente. Revisar entrada.md (cores/fontes do cliente têm prioridade). Trocar imagens genéricas por mídia coerente com o negócio.

## Site ficou compacto/apertado
→ Revisar tokens de espaçamento (escala base 8, padding vertical 6-8rem nas seções). designer-ui deve usar respiro generoso.

## Layout quebrou no mobile
→ Rodar a skill responsivo-fix: testar 360/768/1280, corrigir com clamp(), minmax(), unidades fluidas.

## Como ver o site pronto
→ Pedir ao Claude Code: "suba um servidor local pra eu ver no navegador". Ele roda python -m http.server ou npx serve e dá o endereço.

## Perdi algo / quero voltar atrás
→ Git é a rede de segurança: `git log` pra ver versões, `git checkout <commit>` pra voltar. Faça commit antes de mudanças grandes.

## O sistema está grande e travando o Obsidian
→ Auditar plugins (>30 pesa). Desativar o que não usa. Podar arquivos órfãos com a skill manutencao-cofre.
