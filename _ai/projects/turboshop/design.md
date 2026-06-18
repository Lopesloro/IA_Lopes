# Design — TurboShop

## Tom visual
**Moderno, rápido, premium** — alusão a velocidade (nome "Turbo"), com estética dark + accent vibrante tipo Linear/Vercel/Apple.

## Paleta (HEX, contraste AA verificado)

| Token | Cor | HEX | Uso |
|---|---|---|---|
| `--bg` | Preto carbono | `#0A0A0B` | Fundo principal |
| `--bg-elev` | Grafite | `#141417` | Cards, drawer, modais |
| `--bg-elev-2` | Grafite claro | `#1E1E23` | Hover de cards, inputs |
| `--border` | Linha sutil | `#2A2A30` | Bordas, divisórias |
| `--text` | Branco | `#F5F5F7` | Texto principal (contraste 17:1) |
| `--text-muted` | Cinza médio | `#A1A1AA` | Texto secundário (contraste 6.8:1) |
| `--text-dim` | Cinza escuro | `#71717A` | Labels, metadados |
| `--accent` | Verde-limão neon | `#C7F23C` | CTA primário, preço, contador (contraste 14:1 no bg) |
| `--accent-hover` | Verde-limão claro | `#D4F76A` | Hover do accent |
| `--accent-fg` | Preto carbono | `#0A0A0B` | Texto sobre accent |
| `--success` | Verde esmeralda | `#10B981` | "Adicionado ao carrinho" |
| `--danger` | Vermelho coral | `#EF4444` | Remover item, erro |

**Por quê:** dark mode evita custo de imagens com fundos coloridos (mais elegante pra demo) + accent neon força hierarquia visual clara em CTAs.

## Tipografia
- **Título:** `Space Grotesk` (Google Fonts) — geométrica, tem personalidade de tech/velocidade.
- **Corpo:** `Inter` (Google Fonts) — neutra, ótima leitura.
- **Mono (preço):** `JetBrains Mono` (opcional, pra dar feel de "spec técnica").

**Escala (Major Third, 1.25):**
| Token | rem | px | Uso |
|---|---|---|---|
| `--text-xs` | 0.75rem | 12 | Labels |
| `--text-sm` | 0.875rem | 14 | Meta, secundário |
| `--text-base` | 1rem | 16 | Corpo |
| `--text-lg` | 1.25rem | 20 | Nome do produto |
| `--text-xl` | 1.563rem | 25 | Subtítulos |
| `--text-2xl` | 1.953rem | 31 | Título de seção |
| `--text-3xl` | 2.441rem | 39 | Hero subhead |
| `--text-4xl` | 3.052rem | 49 | Hero título |
| `--text-5xl` | 3.815rem | 61 | Hero título (desktop) |

**Pesos:** 400 (regular), 500 (medium), 600 (semibold), 700 (bold).

## Layout / Grid
- **Container max:** `1280px` (centralizado, padding lateral `1.5rem` mobile / `2rem` desktop)
- **Grid de produtos:** 1 col (mobile) → 2 col (≥640px) → 3 col (≥1024px) → 4 col (≥1280px)
- **Espaçamento base:** escala 4px (`--space-1: 4px` até `--space-16: 64px`)
- **Breakpoints:** 360 / 640 / 768 / 1024 / 1280

## Bordas e elevação
- `--radius-sm: 6px` (botões pequenos, badges)
- `--radius-md: 12px` (cards, inputs)
- `--radius-lg: 20px` (drawer, modal)
- `--radius-full: 9999px` (pill, ícone-círculo)
- `--shadow-md: 0 4px 16px rgba(0,0,0,.4)` (cards em hover)
- `--shadow-lg: 0 20px 40px rgba(0,0,0,.5)` (drawer/modal)

## Animações
- **Hero:** GSAP fade-up nos elementos do hero (stagger 0.1s)
- **Cards:** GSAP ScrollTrigger — fade-up quando entram no viewport
- **Botão "Adicionar":** scale 0.96 no click + flash do accent
- **Drawer do carrinho:** slide da direita, 280ms `cubic-bezier(.4,0,.2,1)`
- **Badge do contador:** pulse rápido ao adicionar item

## Tokens CSS (prontos pra colar em `:root`)

```css
:root {
  /* Cores */
  --bg: #0A0A0B;
  --bg-elev: #141417;
  --bg-elev-2: #1E1E23;
  --border: #2A2A30;
  --text: #F5F5F7;
  --text-muted: #A1A1AA;
  --text-dim: #71717A;
  --accent: #C7F23C;
  --accent-hover: #D4F76A;
  --accent-fg: #0A0A0B;
  --success: #10B981;
  --danger: #EF4444;

  /* Tipografia */
  --font-display: 'Space Grotesk', system-ui, sans-serif;
  --font-body: 'Inter', system-ui, sans-serif;
  --font-mono: 'JetBrains Mono', ui-monospace, monospace;

  --text-xs: 0.75rem;
  --text-sm: 0.875rem;
  --text-base: 1rem;
  --text-lg: 1.25rem;
  --text-xl: 1.563rem;
  --text-2xl: 1.953rem;
  --text-3xl: 2.441rem;
  --text-4xl: 3.052rem;
  --text-5xl: 3.815rem;

  /* Espaçamento */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 20px;
  --space-6: 24px;
  --space-8: 32px;
  --space-10: 40px;
  --space-12: 48px;
  --space-16: 64px;

  /* Bordas */
  --radius-sm: 6px;
  --radius-md: 12px;
  --radius-lg: 20px;
  --radius-full: 9999px;

  /* Sombras */
  --shadow-md: 0 4px 16px rgba(0,0,0,.4);
  --shadow-lg: 0 20px 40px rgba(0,0,0,.5);

  /* Container */
  --container-max: 1280px;

  /* Transições */
  --ease-out: cubic-bezier(.4, 0, .2, 1);
  --dur-fast: 150ms;
  --dur-base: 280ms;
}
```

## Componentes (mapa)
- **Header (fixo):** logo "TurboShop ⚡" + nav (categorias) + ícone carrinho com badge
- **Hero:** título grande + subtítulo + CTA "Explorar" → scroll suave para vitrine
- **Card de produto:** imagem 4:5, categoria (text-dim, uppercase, xs), nome (lg, semibold), preço (mono, accent), botão "Adicionar" full-width
- **Drawer do carrinho:** slide direita, lista de itens (imagem + nome + qty + remover), subtotal e total (accent), botão "Finalizar" (mostra modal de "demo")
- **Modal de detalhes:** imagem maior, descrição completa, preço, "Adicionar"
- **Footer:** logo + copyright + links fake

**Ícones (Lucide):** `shopping-cart`, `x`, `plus`, `minus`, `trash-2`, `zap` (logo), `arrow-right`, `chevron-down`.

---
--- HANDOFF ---
De: designer-ui
Fase concluída: Fase 2 — Design
Resultado: Paleta dark + accent verde-limão `#C7F23C`. Fontes Space Grotesk/Inter. Tokens CSS prontos pra colar. Layout grid responsivo 1→4 colunas. Animações GSAP definidas.
Aguardando do dono: aprovar o design (paleta/fontes/tokens), ou pedir ajustes (ex: trocar accent, mudar fonte, modo claro em vez de dark).
Próximo agente: Fase 3 — implementação. Vou pedir **aprovação explícita pra sair do cofre** e escrever em `C:\Projetos\turboshop\`.
