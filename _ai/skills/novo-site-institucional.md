# Skill: Novo Site Institucional
> Versão profissional. Usada na FASE 3 do [[PIPELINE-novosite]] pelo [[arquiteto-frontend]]. Ver [[INDEX]] · [[PROTOCOLO]].

## Objetivo
Entregar um site institucional que pareça feito por estúdio, não por template. O que separa profissional de mediano não é "ter as seções" — é ritmo visual, tipografia com intenção, movimento sutil e detalhes consistentes.

## Padrão de qualidade (o que estamos perseguindo)
Sites de referência pra estudar o nível (Awwwards Site of the Day): observe neles — hero com uma ideia só e muito respiro, tipografia grande e confiante, paleta enxuta (1 cor de destaque), microinterações no hover, scroll com revelação suave. Exemplos de padrões premiados em 2026: fintechs em preto-e-branco com UMA cor de CTA (laranja), scroll cinematográfico, e performance impecável apesar do visual pesado. A régua: se não daria pra postar no Behance sem vergonha, não está pronto.

## Stack
HTML5 semântico · CSS com custom properties (sem framework pesado) · JS vanilla · GSAP + ScrollTrigger (CDN, grátis) · Lucide icons · fontes via Fontshare/Google Fonts self-host.

## Estrutura de arquivos
```
/index.html
/css/  reset.css  tokens.css  style.css
/js/   main.js
/assets/img/   /assets/fonts/   /assets/icons/
```

## Processo
1. Ler `design.md` do projeto (tokens já definidos pelo [[designer-ui]]). Se não houver, rodar [[design-tokens]] antes.
2. Montar o HTML semântico: header, hero, prova social, serviços, sobre, portfólio/cases, CTA, contato, footer.
3. Aplicar tokens (cores, tipografia, espaçamento) — NUNCA valores soltos no meio do CSS.
4. Adicionar movimento: reveal no scroll (sutil, 0.4-0.6s, ease-out), hover nos cards/botões.
5. SEO + acessibilidade + performance (ver checklists abaixo).
6. Rodar [[auditar-performance]] antes de entregar.

## EXEMPLO — tokens CSS (este é o nível esperado)
```css
:root{
  /* cor: paleta enxuta, 1 destaque */
  --bg:#0c0c0e; --surface:#16161a; --text:#f4f4f5; --muted:#a1a1aa;
  --accent:#ff5a1f; --accent-hover:#ff7847;
  /* tipografia com escala (major third 1.25) */
  --font-display:"Clash Display",sans-serif; --font-body:"Inter",sans-serif;
  --step--1:.8rem; --step-0:1rem; --step-1:1.25rem; --step-2:1.563rem;
  --step-3:1.953rem; --step-4:2.441rem; --step-5:clamp(2.5rem,6vw,4.5rem);
  /* espaçamento base 8 */
  --space-xs:.5rem; --space-s:1rem; --space-m:2rem; --space-l:4rem; --space-xl:8rem;
  --maxw:1200px; --radius:14px;
}
```

## EXEMPLO — hero que respira (não o hero genérico de template)
```html
<section class="hero">
  <p class="hero__eyebrow">Tratamento de água industrial</p>
  <h1 class="hero__title">Água tratada do jeito certo, <span>sem desperdício</span>.</h1>
  <p class="hero__lead">Soluções B2B para indústrias que não podem parar.</p>
  <a class="btn btn--accent" href="#contato">Falar com especialista</a>
</section>
```
```css
.hero{min-height:88vh;display:grid;align-content:center;gap:var(--space-s);
  max-width:var(--maxw);margin-inline:auto;padding:var(--space-l) var(--space-m);}
.hero__eyebrow{color:var(--accent);text-transform:uppercase;letter-spacing:.15em;font-size:var(--step--1);}
.hero__title{font-family:var(--font-display);font-size:var(--step-5);line-height:1.05;max-width:18ch;}
.hero__title span{color:var(--accent);}
.hero__lead{color:var(--muted);font-size:var(--step-1);max-width:48ch;}
```

## EXEMPLO — reveal sutil no scroll
```js
import {gsap} from "gsap"; import {ScrollTrigger} from "gsap/ScrollTrigger";
gsap.registerPlugin(ScrollTrigger);
gsap.utils.toArray("[data-reveal]").forEach(el=>{
  gsap.from(el,{y:32,opacity:0,duration:.6,ease:"power2.out",
    scrollTrigger:{trigger:el,start:"top 85%"}});
});
```

## ✅ ANTI-PADRÕES (NUNCA faça)
- ❌ Hero com 3 botões competindo — UMA ação principal só.
- ❌ Mais de 2 famílias de fonte, ou fonte de sistema "Arial" como display.
- ❌ Gradiente arco-íris, sombra exagerada (box-shadow:0 0 50px), border-radius diferente em cada card.
- ❌ Texto cinza-claro sobre branco (contraste abaixo de 4.5:1).
- ❌ Animação que dura >0.8s ou faz a página "pular" (anima só transform/opacity).
- ❌ Carrossel automático no hero (mata conversão e acessibilidade).
- ❌ "Lorem ipsum" na entrega — sempre conteúdo real ou placeholder coerente.
- ❌ Valores mágicos soltos no CSS (#3a3a3a aqui, 17px ali) — tudo via token.
- ❌ Imagens sem otimizar (PNG de 2MB) — WebP/AVIF, lazy.

## ✅ CHECKLIST DE ENTREGA (critério de sucesso)
- [ ] Lighthouse ≥ 90 em Performance, SEO, Acessibilidade, Best Practices
- [ ] LCP < 2.5s · CLS < 0.1 · INP < 200ms
- [ ] Responsivo testado em 360 / 768 / 1280 / 1920
- [ ] Contraste AA em todo texto
- [ ] 1 H1, hierarquia de heading correta, alt em imagens
- [ ] Favicon + Open Graph + meta description
- [ ] Formulário funcional (ou WhatsApp) + estados de erro/sucesso
- [ ] Zero erro no console
- [ ] Passa no teste "Behance": eu postaria sem vergonha?

## Regra
Código fora de _ai/ → pedir aprovação antes de escrever. Não entrega com item crítico do checklist aberto.
