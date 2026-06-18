# Auditoria — TurboShop
> Pipeline: `/novosite` · Fase 4 · Data: 2026-06-15

## Resumo executivo
Site funcional, semântico e visualmente coerente com o design aprovado. Tem **2 problemas críticos de acessibilidade** e alguns ajustes importantes de SEO/UX antes de chamar de "pronto pra cliente". Performance e estrutura estão bem.

## Achados

| # | Problema | Severidade | Impacto | Como corrigir |
|---|---|---|---|---|
| A1 | Drawer e modal sem `role="dialog"`, `aria-modal="true"` e `aria-labelledby` | **Crítico** | Leitores de tela não anunciam como diálogo; usuário fica "perdido" no DOM | Adicionar atributos ARIA + `tabindex="-1"` no container + foco inicial no botão fechar |
| A2 | Toast sem `aria-live="polite"` e `role="status"` | **Crítico** | Usuário de leitor de tela não escuta confirmação "adicionado" | Adicionar `role="status"` e `aria-live="polite"` no `#toast` |
| A3 | Botão "Carrinho" sem `aria-expanded` / `aria-controls` | Importante | Estado do drawer não é exposto | Setar `aria-expanded` dinamicamente; vincular ao `id` do drawer |
| S1 | Sem favicon (erro 404 no console) | Importante | Profissionalismo + erro no DevTools | Adicionar `<link rel="icon">` (mesmo SVG inline com o "zap") |
| S2 | Sem Open Graph / Twitter Cards | Importante | Compartilhamento em redes fica feio | Adicionar `og:title`, `og:description`, `og:image`, `og:type=website` |
| S3 | Foco não fica preso no drawer/modal | Importante | Tab "escapa" do diálogo aberto | Implementar focus trap simples (loop entre primeiro/último focusable) |
| P1 | Tailwind via CDN imprime warning no console | Sugestão | OK pra demo, ruim pra produção | Em produção real, migrar pra build com Tailwind CLI ou Astro |
| P2 | Imagens Unsplash sem `width`/`height` explícitos | Sugestão | Pode contribuir pra CLS | Definir `width`/`height` no `<img>` ou `aspect-ratio` já garante (já garante via CSS) — risco baixo |
| P3 | Sem `preload` da fonte de display | Sugestão | LCP marginalmente melhor | `<link rel="preload" as="font" ...>` para Space Grotesk 700 |
| T1 | Sem Schema.org / JSON-LD de Product | Sugestão | SEO de produto / rich results | Adicionar JSON-LD por produto (não vale a pena pra demo) |
| T2 | Sem `noscript` fallback | Sugestão | JS desabilitado mostra página vazia | Aceitável pra demo (SPA-like) |

## Pontos fortes
- HTML semântico (`header`, `section`, `article`, `aside`, `footer`)
- H1 único e descritivo
- Imagens com `alt` real
- `loading="lazy"` nas imagens dos cards
- Esc fecha drawer e modal
- Persistência do carrinho versionada (`turboshop:cart:v1`)
- Contraste de cores validado (AA) no design
- Preconnect dos domínios de fontes
- Smooth scroll por CSS

## Métricas-alvo (estimativa — para verificar com Lighthouse real)
- **LCP:** provavelmente < 2.5s (LCP é o H1, fontes com `display=swap`) ✓
- **CLS:** baixo, mas verificar imagens (P2) ✓
- **INP:** baixo, listeners leves ✓
- **Lighthouse Acessibilidade:** ~85 antes dos fixes / ~95+ depois ⚠️
- **Lighthouse SEO:** ~90 antes / ~100 depois ⚠️
- **Lighthouse Performance:** ~95 (Tailwind CDN não é problema em demo) ✓

## Recomendação
Aplicar os fixes A1, A2, A3 (críticos) + S1, S2, S3 (importantes) antes de considerar entregue. P/T são opcionais pra demo.

## Fixes aplicados (2026-06-15)
- ✅ A1: drawer e modal agora têm `role="dialog"`, `aria-modal="true"`, `aria-labelledby` + `tabindex="-1"`
- ✅ A2: toast com `role="status"` e `aria-live="polite"`
- ✅ A3: botão `#open-cart` com `aria-expanded` dinâmico + `aria-controls="cart-drawer"`
- ✅ S1: favicon SVG inline (raio em accent neon, zero requisição extra)
- ✅ S2: Open Graph + Twitter Cards no `<head>`
- ✅ S3: focus trap implementado em `ui.js` (helper `trapFocus`/`releaseTrap`), foco volta pro elemento que abriu o diálogo

Itens P1–P3 e T1–T2 deixados em aberto (sugestões pra projeto não-demo).

## Deploy (quando quiser publicar)
- **Mais rápido:** [Netlify Drop](https://app.netlify.com/drop) — arrasta a pasta `C:\Projetos\turboshop\` no navegador, recebe URL pública em 30s.
- **Versionado:** push pra GitHub → Cloudflare Pages liga ao repo → deploy automático.
- **Cliente final:** subir os arquivos via FTP na Hostinger (pasta `public_html`).

---
--- HANDOFF ---
De: auditor-performance
Fase concluída: Fase 4 — Auditoria
Resultado: 2 críticos (a11y), 3 importantes, 5 sugestões. Estrutura e perf OK.
Aguardando do dono: aprovação pra **aplicar os fixes críticos + importantes** em `C:\Projetos\turboshop\` (regravar `index.html` + `ui.js`), ou aceitar a demo como está.
Próximo passo: dono decide. Se aprovar, eu corrijo e fecho a entrega.
