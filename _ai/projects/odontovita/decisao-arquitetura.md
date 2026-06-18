# Decisão de Arquitetura — OdontoVita

## Tipo
**Institucional + captação de lead** (single page com âncoras + formulário que dispara WhatsApp).

Justificativa: objetivo é apresentar a clínica e converter em agendamento — sem operação online complexa, sem login, sem catálogo. Single page maximiza scroll-to-CTA e simplifica deploy. Encaixa 100% no stack institucional do briefing.

## Stack escolhida
- **HTML5 semântico + CSS3 + JavaScript vanilla (ES modules)**
- **Tailwind CSS via CDN** (utilitários, sem build)
- **GSAP + ScrollTrigger via CDN** (animações de entrada e scroll)
- **Lucide Icons via CDN** (ícones consistentes e leves)
- **Pollinations.ai** para imagens IA via URL (zero infra)
- **WhatsApp deep link** (`https://wa.me/55... ?text=...`) para receber leads

**Por quê:**
1. Zero build → roda direto em servidor estático.
2. Alinhado com `stack-padrao.md`.
3. Lead vai pro WhatsApp do dentista, sem precisar de servidor de e-mail.
4. Imagens IA via URL eliminam pasta de assets pesada.

## Estrutura de pastas
```
C:\Projetos\odontovita\
├── index.html                # Página única, todas as seções
├── assets/
│   ├── css/
│   │   └── styles.css        # Tokens + estilos custom
│   └── js/
│       ├── data.js           # Serviços, equipe, depoimentos, FAQ
│       ├── form.js           # Validação + redirect WhatsApp
│       ├── ui.js             # Renderização dinâmica + interações (FAQ, etc)
│       └── main.js           # Bootstrap: Lucide, GSAP, listeners
└── README.md                 # Como abrir + como trocar placeholders
```

## Imagens via IA (Pollinations.ai)
Padrão de URL:
```
https://image.pollinations.ai/prompt/{prompt encoded}?width=800&height=1000&nologo=true&seed=N
```
- `seed` fixo por imagem → estabilidade visual entre cargas.
- `width`/`height` adequados ao uso (hero maior, retratos menores).
- `loading="lazy"` em tudo exceto a do hero.
- Catálogo de prompts em `assets/js/data.js` (campo `imgPrompt`) — fácil regerar trocando seed.

**Riscos:** primeira geração pode levar 3–8s. Mitigar com:
- Skeleton/blur placeholder no `<img>` (background com gradiente da paleta).
- Pré-aquecimento: cache de browser nas próximas visitas é instantâneo.

## Fluxo do formulário
1. Usuário preenche (nome, telefone, serviço de interesse, mensagem opcional).
2. `form.js` valida em tempo real (telefone com máscara BR, campos obrigatórios).
3. No submit válido, monta mensagem:
   `Olá! Sou [nome], gostaria de agendar avaliação para [serviço]. Tel: [tel]. [mensagem]`
4. Abre `https://wa.me/5511999990000?text=...` em nova aba.
5. Mostra confirmação visual ("Direcionando pro WhatsApp...").

## Integrações
- **Sem backend.** Tudo client-side.
- **WhatsApp:** deep link (placeholder editável).
- **Mapa:** iframe do Google Maps embed (URL pública, sem API key) ou imagem estática.
- **Sem analytics** (demo); placeholder pra GA4/Plausible no `<head>` documentado.

## Deploy
- **Local:** `python -m http.server 8080` ou Live Server.
- **Produção:** Netlify drop / Cloudflare Pages / Hostinger (estático puro).

## Acessibilidade (já planejado, não posterior)
- `role="dialog"` + focus trap no FAQ aberto? Não — acordeão é `<details>`/`<summary>` nativo (acessível de fábrica).
- Formulário com `<label>` real, `aria-describedby` pra erros, `aria-live` pra mensagens.
- Contraste AA validado no design.
- Imagens IA com `alt` descritivo gerado a partir do prompt.

## Riscos / Trade-offs
- **Pollinations latência primeira carga:** aceitável pra demo; em produção real, considerar gerar e hospedar versões otimizadas.
- **Tailwind CDN:** aceitável em demo.
- **Sem SSR:** OK — site institucional simples indexa bem mesmo SPA-like single page.

## ADR
Registrar em `_ai/decisions/2026-06-15-odontovita.md` após aprovação.

---
--- HANDOFF ---
De: arquiteto-frontend
Fase concluída: Fase 1 — Arquitetura
Resultado: HTML/CSS/JS + Tailwind CDN + GSAP + Lucide. Single page institucional com âncoras. Imagens IA via Pollinations. Form dispara WhatsApp. Pasta `C:\Projetos\odontovita\`.
Aguardando do dono: aprovar a stack, a estrutura e o uso do Pollinations pras imagens IA (ou pedir outra fonte: Unsplash, Midjourney via CDN próprio, etc).
Próximo agente: designer-ui (só inicia após "aprovado").
