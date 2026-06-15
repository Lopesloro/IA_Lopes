# 🧰 Arsenal Web Dev — Ferramentas para Criação de Sites Profissionais

> Catálogo de ferramentas externas para o segundo cérebro. Atualizado em junho/2026.
> Vai do site institucional simples (HTML/CSS/JS puro) até sistema completo (React/Next + backend).
> Coloque isto em `Recursos/` no Obsidian. As skills do Claude Code ficam em `_ai/skills/`.

---

## COMO USAR ESTE ARSENAL

- **Site institucional/landing simples** → seções 1, 2 (CSS), 4 (animação leve), 6 (deploy), 8 (assets).
- **Site com bastante movimento/showroom** → adicione seção 4 (GSAP), 5 (3D), 9 (vídeo/Remotion).
- **Sistema/app web completo** → seções 3 (frameworks), 7 (backend/DB), 10 (auth/pagamento), 11 (estado/forms).
- **Qualquer projeto** → seção 12 (IA), 13 (qualidade/perf), 14 (workflow).

---

## 1. EDITOR E AMBIENTE BASE

| Ferramenta | Para quê | Nota |
|---|---|---|
| **VS Code** | Editor principal | Onde o Claude Code roda |
| **Cursor** | Editor com IA embutida (fork do VS Code) | Alternativa se quiser IA dentro do editor |
| **Claude Code** | Agente de IA no terminal | Seu motor de execução |
| **Chrome DevTools** | Debug, performance, inspeção | Nativo do navegador |
| **Git + GitHub** | Versionamento e CI/CD | Base de tudo |
| **WebStorm** | IDE focada em JS (paga) | Alternativa pesada ao VS Code |

---

## 2. CSS E ESTILIZAÇÃO

| Ferramenta | Para quê | Quando usar |
|---|---|---|
| **Tailwind CSS** | Utilitários de CSS | Padrão de fato pra velocidade |
| **CSS puro + custom properties** | Controle total | Sites institucionais leves (seu forte) |
| **PostCSS / Autoprefixer** | Processar CSS, prefixos | Pipeline de build |
| **Sass/SCSS** | CSS com variáveis, nesting | Projetos sem Tailwind |
| **Open Props** | Variáveis CSS prontas | CSS puro turbinado |
| **CSS-only approaches** | Zero JS, melhor performance | Landing pages rápidas |

**Dica:** pra site institucional puro, CSS + custom properties + um pouco de Tailwind via CDN já entrega resultado profissional sem build.

---

## 3. FRAMEWORKS FRONTEND (do app simples ao mega sistema)

| Framework | Força | Use para |
|---|---|---|
| **React** | Ecossistema gigante, ~45% do mercado | Apps, dashboards, marketplaces |
| **Next.js 16** | React full-stack, SSR/SSG, edge, SEO | Sites que precisam de SEO + app |
| **Astro** | Conteúdo estático rapidíssimo, "ilhas" | Blogs, sites de conteúdo, landing |
| **SvelteKit** | Compilador, runtime mínimo, performance | Apps leves, UIs reativas |
| **Vue / Nuxt** | Curva suave, ótima doc | Alternativa ao React |
| **Qwik** | Resumability, Core Web Vitals altíssimos | Quando performance é tudo |
| **Angular** | Opinativo, type-safe, enterprise | ERP, financeiro, saúde |

**Recomendação pro seu perfil:** Astro pra sites de conteúdo/institucionais (gera HTML estático, encaixa com seu HTML/CSS/JS puro), Next.js quando virar app de verdade.

---

## 4. ANIMAÇÃO WEB (UI e scroll)

| Ferramenta | Tipo | Use para | Licença |
|---|---|---|---|
| **GSAP (GreenSock)** | Imperativo, JS-first | Scroll, timelines, sites "award-winning" | Core grátis; plugins premium pagos* |
| **Motion (ex-Framer Motion)** | Declarativo, React | UI, micro-interações, exit/layout | MIT (grátis) |
| **Anime.js** | Leve, JS | CSS, SVG, timelines | Grátis |
| **React Spring** | Física (springs) | Movimento natural em React | Grátis |
| **CSS / Web Animations API** | Nativo | Transições simples (roda no compositor) | Nativo |
| **AutoAnimate** | 1 linha | Listas que animam sozinhas | Grátis |

\* Plugins pagos do GSAP (ScrollSmoother, MorphSVG, SplitText, DrawSVG) exigem Club GreenSock pra uso comercial. O **ScrollTrigger é grátis** e cobre a maioria dos scroll animations.

**Regra prática:** CSS pra simples → Motion pra UI React → GSAP pra scroll complexo e sequências choreografadas. GSAP funciona em HTML/CSS/JS puro também (não precisa de React).

---

## 5. 3D E VISUAL AVANÇADO

| Ferramenta | Para quê |
|---|---|
| **Three.js** | 3D no navegador (WebGL) |
| **React Three Fiber** | Three.js em React |
| **Spline** | 3D visual (sem código), exporta pra web |
| **Lottie** | Animações vetoriais (After Effects → web) |
| **Rive** | Animações interativas leves |
| **PlayCanvas** | Engine 3D/jogos web |

Útil pro tipo de projeto "showroom interativo, 360°, hotspots" que você já fez.

---

## 6. DEPLOY E HOSPEDAGEM

| Plataforma | Força | Tier grátis |
|---|---|---|
| **Vercel** | Edge-first, perfeito pra Next.js | Sim |
| **Netlify** | Estático + funções, simples | Sim |
| **Cloudflare Pages** | Edge global, rápido | Sim (generoso) |
| **Railway** | Full-stack, banco incluso | Limitado |
| **Render** | Full-stack, simples | Sim |
| **Hostinger** | Hospedagem tradicional BR (você já usa) | Não |
| **GitHub Pages** | Estático grátis | Sim |

**Pro institucional simples:** Netlify ou Cloudflare Pages (arrasta a pasta, está no ar). **Pro app Next.js:** Vercel. **Pro cliente que quer hospedagem própria:** Hostinger.

---

## 7. BACKEND, BANCO E APIS

| Ferramenta | Para quê |
|---|---|
| **Node.js + Express** | Backend JS (seu stack atual) |
| **Fastify** | Express mais rápido |
| **PostgreSQL** | Banco relacional robusto (seu stack) |
| **Supabase** | Postgres + auth + storage + realtime (backend pronto) |
| **Prisma / Drizzle** | ORM type-safe |
| **FastAPI (Python)** | APIs rápidas, se misturar com Python |
| **Hono** | Framework backend edge, minúsculo |
| **tRPC** | API type-safe end-to-end (com TS) |

**Atalho pra "mega sistema" rápido:** Supabase te dá banco + login + storage prontos, economiza semanas.

---

## 8. ASSETS: ÍCONES, FONTES, IMAGENS

| Categoria | Ferramentas |
|---|---|
| **Ícones** | Lucide (padrão moderno), Heroicons, Phosphor, Tabler Icons, Iconify (todos num lugar) |
| **Fontes** | Google Fonts, Fontshare, Fontsource (self-host fácil) |
| **Imagens grátis** | Unsplash, Pexels, Pixabay |
| **Ilustrações** | unDraw, Storyset, Humaaans |
| **Otimização** | Squoosh, TinyPNG, Sharp (no build) |
| **Imagens IA** | (ver seção 12) |
| **SVG** | SVGOMG (otimizar), Hero Patterns (fundos) |
| **Mockups** | Shots.so, Screely |

---

## 9. VÍDEO E CONTEÚDO PROGRAMÁTICO

| Ferramenta | Para quê |
|---|---|
| **Remotion** | Criar vídeos com React (programático) — seu exemplo |
| **FFmpeg** | Processar/converter vídeo no servidor |
| **Mux / Cloudinary** | Hospedar e otimizar vídeo/imagem |
| **Lottie** | Animações leves no lugar de vídeo |

**Sobre Remotion:** é pra *gerar vídeo* via código (intros, vídeos de marketing automatizados, render em massa), não pra animação de UI em tempo real. Encaixa se você quiser oferecer vídeos automatizados aos clientes.

---

## 10. AUTENTICAÇÃO E PAGAMENTO

| Ferramenta | Para quê |
|---|---|
| **Clerk** | Auth pronto, UI bonita |
| **Auth.js (NextAuth)** | Auth pra Next.js |
| **Supabase Auth** | Login junto com o banco |
| **Stripe** | Pagamento internacional |
| **Mercado Pago / Pagar.me / Asaas** | Pagamento BR (Pix, boleto, cartão) |
| **bcrypt + Helmet.js** | Segurança manual (você já usa) |

---

## 11. ESTADO, FORMULÁRIOS E DADOS (React)

| Ferramenta | Para quê |
|---|---|
| **Zustand** | Estado global simples |
| **TanStack Query (React Query)** | Cache de dados de API |
| **React Hook Form** | Formulários performáticos |
| **Zod** | Validação type-safe (forms + API) |
| **shadcn/ui** | Componentes copy-paste (Radix + Tailwind), você é dono do código |
| **Radix UI** | Primitivos acessíveis sem estilo |
| **daisyUI** | Componentes Tailwind por classe (sem JS) |
| **Recharts / Chart.js** | Gráficos |
| **TanStack Table** | Tabelas com sort/paginação |

**Combo campeão 2026 pra dashboards:** shadcn/ui + React Hook Form + Zod + TanStack Query.

---

## 12. IA PRA CÓDIGO E ASSETS

| Ferramenta | Para quê |
|---|---|
| **Claude Code** | Agente de código no terminal (seu motor) |
| **GitHub Copilot** | Autocomplete no editor |
| **Cursor** | Editor IA-first |
| **v0 (Vercel)** | Gera UI React/Tailwind a partir de prompt |
| **Midjourney / DALL·E / Flux** | Imagens geradas |
| **Recraft** | Imagens/ilustrações vetoriais por IA |
| **Cloudinary AI** | Otimização e edição de imagem por IA |

---

## 13. QUALIDADE, PERFORMANCE E SEO

| Ferramenta | Para quê |
|---|---|
| **Lighthouse** | Auditoria (perf, SEO, acessibilidade) — no DevTools |
| **PageSpeed Insights** | Core Web Vitals reais |
| **ESLint + Prettier** | Lint e formatação |
| **TypeScript** | Tipagem (menos bugs) |
| **Vitest / Playwright** | Testes unitários / e2e |
| **WAVE / axe** | Acessibilidade |
| **Schema.org / JSON-LD** | SEO estruturado |

---

## 14. WORKFLOW E PRODUTIVIDADE

| Ferramenta | Para quê |
|---|---|
| **Vite** | Build/dev server rapidíssimo |
| **pnpm** | Gerenciador de pacotes rápido |
| **Bun** | Runtime + package manager all-in-one |
| **Figma** | Design e protótipo |
| **Storybook** | Catálogo de componentes |
| **Postman / Bruno** | Testar APIs |
| **Responsively** | Ver site em vários tamanhos de tela |

---

## STACKS RECOMENDADAS (atalho de decisão)

**Site institucional simples (cliente pequeno):**
HTML/CSS/JS puro + Tailwind CDN + GSAP ScrollTrigger + Lucide + Netlify. Hospedagem Hostinger se o cliente quiser.

**Landing/site de conteúdo com SEO:**
Astro + Tailwind + Motion + Vercel/Cloudflare.

**Showroom interativo (tipo o da SMTS):**
HTML/CSS/JS ou Astro + GSAP + Three.js/Spline + Lottie + Cloudflare.

**App/dashboard completo:**
Next.js 16 + TypeScript + shadcn/ui + Tailwind + Zustand + TanStack Query + React Hook Form + Zod + Supabase (ou Express+Postgres) + Stripe/Mercado Pago + Vercel.

**Vídeos automatizados pra marketing:**
Remotion + FFmpeg + Mux.
