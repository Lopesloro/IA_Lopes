# Skill: Auditar Performance
> Checklist completo de auditoria de site antes da entrega. Usada pelo [[auditor-performance]] na última fase do [[PIPELINE-novosite]]. Ver [[INDEX]] · [[PROTOCOLO]].

## Quando rodar
Antes de qualquer entrega ao cliente. Também pode ser chamada na fase 3 ([[novo-site-institucional]]) como check intermediário.

## Métricas-alvo (não-negociáveis)
- **LCP** (Largest Contentful Paint) < 2.5s
- **CLS** (Cumulative Layout Shift) < 0.1
- **INP** (Interaction to Next Paint) < 200ms
- **Lighthouse** ≥ 90 em Performance, SEO, Acessibilidade, Best Practices

## Checklist — Performance
- [ ] Imagens otimizadas (WebP/AVIF, `srcset`/`sizes`, `loading="lazy"`)
- [ ] Imagens com `width`/`height` ou `aspect-ratio` (evita CLS)
- [ ] Fontes self-host ou `font-display: swap`; pré-carregar só as críticas
- [ ] CSS crítico inline / above-the-fold priorizado
- [ ] Scripts de terceiros com `async`/`defer`
- [ ] Code-splitting (Next/Astro) para rotas pesadas
- [ ] Animações só em `transform`/`opacity` (não em `width`/`height`)
- [ ] Skeleton/placeholder em vez de spinner pra esperas > 1s

## Checklist — SEO
- [ ] `<title>` único e descritivo (50-60 chars) em cada página
- [ ] Meta description (140-160 chars) em cada página
- [ ] 1 `<h1>` por página, hierarquia de headings sequencial (h2 → h3, sem pular)
- [ ] Open Graph (`og:title`, `og:description`, `og:image`)
- [ ] Twitter Card
- [ ] `sitemap.xml` + `robots.txt`
- [ ] URLs limpas e semânticas (sem `?id=123`)
- [ ] `<link rel="canonical">` quando aplicável
- [ ] Schema.org JSON-LD (LocalBusiness, Product, Article — conforme o caso)

## Checklist — Acessibilidade
- [ ] Contraste **AA** (4.5:1) em todo texto; texto grande 3:1
- [ ] `alt` em TODA imagem (vazio `alt=""` se decorativa)
- [ ] Foco visível em links/botões (`:focus-visible`)
- [ ] `aria-label` em botões só com ícone
- [ ] Tab order coerente com o visual; navegação 100% por teclado
- [ ] Form com `<label for="...">` ligado a cada input
- [ ] Erro de form próximo do campo (não só topo)
- [ ] `prefers-reduced-motion` respeitado em animações
- [ ] Sem texto cinza-sobre-cinza ilegível

## Checklist — Responsivo
- [ ] Testado em 360 / 768 / 1280 / 1920 px
- [ ] Sem scroll horizontal em nenhum breakpoint
- [ ] `viewport` meta correto, sem `user-scalable=no`
- [ ] Toque mínimo 44×44px em mobile
- [ ] Vídeo do hero com fallback ou troca por imagem em mobile (ver [[midia-hero]])

## Checklist — Técnico / Segurança
- [ ] Zero erro/warning no console
- [ ] HTTPS obrigatório
- [ ] Headers de segurança (CSP básico, X-Frame-Options, Referrer-Policy)
- [ ] Sem secrets no front (chaves de API expostas)
- [ ] Form com proteção anti-spam (honeypot/rate-limit)
- [ ] Aviso LGPD no form
- [ ] Favicon + manifest.json
- [ ] 404 customizada
- [ ] Analytics instalado (Plausible/GA)

## Como rodar
1. `npx unlighthouse` ou Lighthouse no DevTools (Mobile + Desktop).
2. PageSpeed Insights (https://pagespeed.web.dev).
3. WebPageTest (https://webpagetest.org) — opcional, mais detalhado.
4. axe DevTools ou WAVE para acessibilidade.
5. Validar HTML em https://validator.w3.org.

## Saída
Tabela em `_ai/outputs/<slug>-auditoria.md`:

| Problema | Severidade | Impacto | Como corrigir |
|---|---|---|---|
| ex: Imagem hero 1.2MB | 🔴 crítico | LCP 4.1s | Converter pra WebP, lazy below-fold |

Severidade: 🔴 crítico (bloqueia entrega) · 🟡 importante · 🔵 sugestão.

## Regra
Não entrega com 🔴 crítico aberto. Aponta, propõe correção, não maquia.
