# Decisão de Arquitetura — TurboShop

## Tipo
**Institucional/vitrine com interatividade leve** (e-commerce demo, sem checkout real).
Justificativa: o briefing pede um carrinho funcional + persistência local, mas sem backend/auth/pagamento. Não justifica Next.js. Encaixa perfeito no stack institucional do briefing.

## Stack escolhida
- **HTML5 semântico + CSS3 + JavaScript vanilla (ES modules)**
- **Tailwind CSS via CDN** (sem build)
- **GSAP + ScrollTrigger via CDN** (animações de entrada e scroll)
- **Lucide Icons via CDN** (ícones consistentes)
- **localStorage** (persistência do carrinho)
- **Unsplash** (imagens de produto via URL pública)

**Por quê:**
1. Zero build → roda abrindo `index.html` direto no navegador (ideal pra teste).
2. Alinha 100% com `stack-padrao.md` (HTML/CSS/JS + Tailwind CDN + GSAP + Lucide).
3. Carrinho via `localStorage` cobre 100% do escopo sem servidor.
4. Performance excelente por padrão (sem hidratação, sem bundle).

## Estrutura de pastas
```
C:\Projetos\turboshop\
├── index.html              # Home (hero + vitrine)
├── assets/
│   ├── css/
│   │   └── styles.css      # Tokens + estilos custom (complementa Tailwind)
│   └── js/
│       ├── data.js         # Catálogo de produtos (array de objetos)
│       ├── cart.js         # Lógica do carrinho (add/remove/total + localStorage)
│       ├── ui.js           # Renderização (cards, drawer do carrinho, modal)
│       └── main.js         # Bootstrap: inicializa ícones, GSAP, listeners
└── README.md               # Como abrir/testar
```

## Fluxo de dados
1. `data.js` exporta `PRODUCTS` (array com id, nome, preço, imagem, categoria, descrição)
2. `ui.js` renderiza os cards a partir de `PRODUCTS`
3. Click em "Adicionar" → `cart.js` adiciona ao estado interno e grava no `localStorage`
4. Drawer do carrinho lê o estado e renderiza itens + total
5. Botão "Detalhes" abre modal com info do produto

## Integrações
- **Sem backend.** Tudo client-side.
- **Sem gateway de pagamento.** Botão "Finalizar" mostra um alerta/modal de "demo".
- **Sem CMS.** Catálogo hardcoded em `data.js`.

## Deploy
- **Local:** abrir `index.html` no navegador (file://) ou rodar `python -m http.server` na pasta.
- **Se quiser publicar depois:** Netlify drop (arrasta pasta), Cloudflare Pages, ou GitHub Pages. Zero config.

## Riscos / Trade-offs
- **Tailwind via CDN:** ótimo pra protótipo, mas em produção real geraria CSS maior que o necessário. OK pra demo.
- **GSAP plugins pagos:** vamos usar só ScrollTrigger (grátis). Nada de SplitText/MorphSVG.
- **SEO limitado:** sem SSR. Não é problema, é demo interna.
- **Sem TypeScript:** aceitável dado o escopo. JSDoc opcional se quiser tipagem leve.

## ADR
Registrar em `_ai/decisions/2026-06-15-turboshop.md` após aprovação.

---
--- HANDOFF ---
De: arquiteto-frontend
Fase concluída: Fase 1 — Arquitetura
Resultado: Stack HTML/CSS/JS + Tailwind CDN + GSAP + Lucide. Carrinho via localStorage. Pasta `C:\Projetos\turboshop\` com estrutura simples (index + assets/css + assets/js).
Aguardando do dono: aprovar a stack e a estrutura, ou pedir ajustes (ex: trocar GSAP por Motion, adicionar TypeScript, mudar a estrutura de pastas).
Próximo agente: designer-ui (só inicia após "aprovado").
