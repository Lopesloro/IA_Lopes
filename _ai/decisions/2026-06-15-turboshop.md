# ADR — TurboShop
> Data: 2026-06-15 · Projeto: turboshop · Status: em vigor

## Contexto
Demo do pipeline `/novosite`. Site funcional de e-commerce com vitrine e carrinho, sem backend.

## Decisões
1. **Stack:** HTML/CSS/JS puro + Tailwind CDN + GSAP + Lucide (alinhado com `stack-padrao.md`).
2. **Persistência:** `localStorage` (chave `turboshop:cart:v1`).
3. **Sem build:** abre via servidor estático local (`python -m http.server`) ou hospedagem estática (Netlify/Cloudflare).
4. **Imagens:** Unsplash via URL pública (sem hospedar assets).
5. **Paleta:** dark mode com accent neon `#C7F23C`.

## Trade-offs aceitos
- Tailwind CDN: aceitável em demo, migrar pra build em projeto real.
- Sem TS: escopo pequeno não justifica.
- Sem SSR/SEO avançado: é demo interna.

## Consequências
- Site é reproduzível em qualquer máquina sem instalar nada além de um servidor estático.
- Carrinho persiste entre sessões no mesmo navegador.
- Não há analytics, A/B test ou tracking.
