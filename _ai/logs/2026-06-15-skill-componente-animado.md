# Skill `componente-animado` — versão profissional

**Data:** 2026-06-15

## Mudança
Criado `_ai/skills/componente-animado.md` em versão profissional com exemplos de código.

## Conteúdo adicionado
- Árvore de decisão (CSS / Motion / GSAP / React Spring) por tipo de uso.
- **Regra de ouro anti-trava:** animar APENAS `transform` e `opacity` (GPU, sem reflow).
- Exemplos Motion: `FadeIn`, `CardHover`, stagger de lista.
- Exemplo de respeito ao `prefers-reduced-motion` com `useReducedMotion`.
- Exemplo GSAP + ScrollTrigger para sites institucionais HTML puro.
- Anti-padrões: prop `layout` em listas grandes, animar width/height/top/left, durações longas, `whileInView` sem `once: true`.
- Nota de licenciamento: Motion MIT; GSAP core grátis, plugins pagos (ScrollSmoother/SplitText/MorphSVG); ScrollTrigger grátis.

## Por que importa
Skill agora tem código copiável e regra clara pra evitar trava em mobile mid-range (Android é o gargalo). Caso mais comum dele = GSAP em institucional HTML puro.

## Itens não tocados
Nenhum site, nenhum outro agente/skill. Mudança contida em `_ai/skills/`.
