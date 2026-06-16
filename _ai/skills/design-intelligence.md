# Skill: Design Intelligence (ui-ux-pro-max)
> Conecta o cérebro ao plugin externo `ui-ux-pro-max-skill` (NextLevelBuilder) — design intelligence de nível profissional. Usado pelo [[designer-ui]]. Ver [[INDEX]] · [[PROTOCOLO]].

## O que é
Plugin do Claude Code (v2.5.0+, MIT) com **7 sub-skills** prontas e base de conhecimento searchável:
- **67 estilos de UI** · **161 paletas de cores** · **57 pares de fontes**
- **99 diretrizes de UX** · **25 tipos de gráfico** · **161 tipos de produto** com regras de raciocínio
- Suporte a 10+ stacks (React, Next.js, Vue, Svelte, Astro, SwiftUI, React Native, Flutter, Tailwind, shadcn/ui, HTML/CSS).

Home: https://uupm.cc · Repo: https://github.com/nextlevelbuilder/ui-ux-pro-max-skill

## Sub-skills do plugin (quando invocar cada uma)
| Sub-skill | Pra quê serve | Quando o designer-ui chama |
|---|---|---|
| `ui-ux-pro-max` | Entrada principal — design intelligence completo | Decidir estilo geral + checar anti-padrões |
| `design-system` | Tokens (primitive/semantic/component), Tailwind | Montar `:root{...}` e tokens do blueprint |
| `design` | Estilos UI, CIP (creative identity prompt), ícones, logo | Definir o LOOK visual do projeto |
| `brand` | Identidade visual, paleta de marca, voz, tipografia | Quando há identidade do cliente em entrada.md |
| `ui-styling` | Biblioteca grande de estilos prontos (102 arquivos) | Buscar exemplos por estilo/componente |
| `banner-design` | Tamanhos e estilos de banner | Hero, redes, anúncios |
| `slides` | Geração de slides/apresentações | Fora do escopo padrão de /novosite |

## Prioridades de design (do SKILL.md oficial — 1→10)
1. **Acessibilidade** (CRÍTICO): contraste 4.5:1, alt text, foco visível, keyboard nav, ARIA.
2. **Touch & Interação** (CRÍTICO): alvo min 44×44px, espaço ≥8px, feedback de loading.
3. **Performance** (ALTA): WebP/AVIF, lazy load, reserva de espaço (CLS<0.1).
4. **Seleção de estilo** (ALTA): combinar com o tipo de produto, SVG (nunca emoji como ícone).
5. **Layout/Responsivo** (ALTA): mobile-first, sem scroll horizontal, viewport meta.
6. **Tipografia/Cor** (MÉDIA): base 16px, line-height 1.5, tokens semânticos.
7. **Animação** (MÉDIA): 150-300ms, motion com significado, prefers-reduced-motion.
8. **Formulários/Feedback** (MÉDIA): labels visíveis, erro próximo do campo.
9. **Navegação** (ALTA): bottom-nav ≤5 itens, back previsível, deep links.
10. **Charts** (BAIXA): legendas, tooltips, cores acessíveis.

## Como usar no fluxo /novosite
1. [[designer-ui]] identifica o tipo de produto (puxa de `entrada.md` + `pesquisa.md`).
2. Invoca `ui-ux-pro-max` pra um design system tailor-made (estilo + paleta + tipografia).
3. **Identidade real do cliente (entrada.md) > sugestão genérica do plugin** — sempre.
4. Roda checagem das prioridades 1-10 antes de fechar o design no blueprint.
5. Leva tokens prontos pro campo "Design" do blueprint.

## Instalação (você executa quando quiser — eu NÃO rodo)
Três opções:
- **Plugin (recomendado):** `/plugin marketplace add nextlevelbuilder/ui-ux-pro-max-skill` → `/plugin install ui-ux-pro-max@ui-ux-pro-max-skill`
- **CLI npm:** `npx uipro-cli init --ai claude`
- **Manual:** `git clone https://github.com/nextlevelbuilder/ui-ux-pro-max-skill.git`

**Pré-requisitos:** Python 3.x (scripts de busca) · Node (para scripts CJS).

## Fallback (se o plugin não estiver instalado)
O [[designer-ui]] segue o fluxo atual sem o plugin: identidade do cliente + boas práticas + [[design-tokens]]. O plugin é POTENCIALIZADOR, não bloqueador.

## Regra
Plugin é fonte; [[designer-ui]] é o decisor. Identidade do cliente > sugestão genérica. Sempre validar contraste AA.
