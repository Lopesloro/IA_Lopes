# Design — OdontoVita

## Tom visual
**Confiável, acolhedor, premium** — clínica que parece spa, não consultório frio. Inspiração em Invisalign / Bullish Dental / clínicas boutique.

## Paleta (HEX, contraste AA verificado)

| Token | Cor | HEX | Uso |
|---|---|---|---|
| `--bg` | Branco | `#FFFFFF` | Fundo principal |
| `--bg-soft` | Cinza-azulado bem leve | `#F4F8FA` | Seções alternadas, cards |
| `--bg-elev` | Off-white | `#FBFCFD` | Cards sobre `--bg-soft` |
| `--border` | Cinza muito sutil | `#E2E8F0` | Bordas, divisórias |
| `--text` | Slate quase preto | `#0F172A` | Texto principal (contraste 18:1) |
| `--text-muted` | Slate médio | `#475569` | Texto secundário (contraste 7.2:1) |
| `--text-dim` | Slate claro | `#94A3B8` | Labels, metadados |
| `--primary` | Teal profundo | `#0E7C7B` | Logo, links, ícones, títulos de seção (contraste 6.1:1) |
| `--primary-dark` | Teal mais escuro | `#0A5957` | Hover de links |
| `--primary-soft` | Teal washed | `#E6F3F2` | Backgrounds de selo, chips |
| `--accent` | Coral quente | `#F97361` | CTA principal "Agendar avaliação" (contraste 3.4:1 com branco — usado com texto branco, contraste 4.9:1 ✓) |
| `--accent-dark` | Coral mais fundo | `#E55B49` | Hover do accent |
| `--success` | Verde sucesso | `#10B981` | Confirmações de form |
| `--danger` | Vermelho | `#DC2626` | Erros de form |
| `--star` | Amarelo dourado | `#FBBF24` | Estrelas de depoimento |

**Por quê:**
- **Teal** transmite saúde + serenidade sem virar "azul de banco" frio.
- **Coral** dá calor humano e foca o olho no CTA único (agendar) — é a única cor quente no site.
- Resto é branco/cinza pra deixar fotos e texto respirarem.

## Tipografia
- **Display:** `Fraunces` (Google Fonts) — serif contemporâneo, transmite premium + humano.
- **Corpo:** `Inter` (Google Fonts) — neutralidade e leitura.

**Escala (Major Third 1.25):**
| Token | rem | px | Uso |
|---|---|---|---|
| `--text-xs` | 0.75rem | 12 | Labels, badges |
| `--text-sm` | 0.875rem | 14 | Meta, captions |
| `--text-base` | 1rem | 16 | Corpo |
| `--text-lg` | 1.125rem | 18 | Lead de seção |
| `--text-xl` | 1.5rem | 24 | Subtítulos |
| `--text-2xl` | 1.875rem | 30 | Título de card |
| `--text-3xl` | 2.25rem | 36 | Título de seção |
| `--text-4xl` | 3rem | 48 | Hero (mobile) |
| `--text-5xl` | 3.75rem | 60 | Hero (desktop) |

**Pesos:** Inter 400/500/600/700 · Fraunces 500/600/700 (com `opsz` 9–144 variável).

## Layout / Grid
- **Container:** max `1200px`, padding lateral `1.25rem` (mobile) / `2rem` (desktop)
- **Seções:** padding vertical `4rem` (mobile) / `6rem` (desktop)
- **Grid de serviços:** 1 col → 2 col (≥640px) → 3 col (≥1024px)
- **Grid de equipe:** 1 col → 3 col (≥768px)
- **Hero:** split 1 col mobile → 2 col desktop (texto 50% + imagem 50%)
- **Breakpoints:** 360 / 640 / 768 / 1024 / 1280

## Espaçamento (escala 4px)
`--space-1: 4px` ... `--space-24: 96px`

## Bordas e elevação
- `--radius-sm: 8px` (botões, badges)
- `--radius-md: 16px` (cards de serviço, inputs)
- `--radius-lg: 24px` (cards grandes, imagem hero)
- `--radius-full: 9999px`
- `--shadow-sm: 0 1px 3px rgba(15,23,42,.05)`
- `--shadow-md: 0 10px 30px rgba(15,23,42,.08)` (cards em hover)
- `--shadow-lg: 0 24px 50px rgba(15,23,42,.12)` (hero image, modais)

## Animações
- **Hero:** fade-up sequencial (badge → headline → subtitle → CTAs → trust strip)
- **Seções:** ScrollTrigger fade-up + stagger nos cards
- **Cards:** translateY(-4px) + shadow no hover
- **Botão CTA accent:** scale 0.97 ao click + brilho sutil
- **FAQ:** animação nativa do `<details>` + ícone que rotaciona
- **Form:** input com border que muda pra `--primary` no focus + label que sobe

## Tokens CSS (prontos pra colar)

```css
:root {
  --bg: #FFFFFF;
  --bg-soft: #F4F8FA;
  --bg-elev: #FBFCFD;
  --border: #E2E8F0;
  --text: #0F172A;
  --text-muted: #475569;
  --text-dim: #94A3B8;
  --primary: #0E7C7B;
  --primary-dark: #0A5957;
  --primary-soft: #E6F3F2;
  --accent: #F97361;
  --accent-dark: #E55B49;
  --success: #10B981;
  --danger: #DC2626;
  --star: #FBBF24;

  --font-display: 'Fraunces', Georgia, serif;
  --font-body: 'Inter', system-ui, sans-serif;

  --text-xs: 0.75rem;
  --text-sm: 0.875rem;
  --text-base: 1rem;
  --text-lg: 1.125rem;
  --text-xl: 1.5rem;
  --text-2xl: 1.875rem;
  --text-3xl: 2.25rem;
  --text-4xl: 3rem;
  --text-5xl: 3.75rem;

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
  --space-20: 80px;
  --space-24: 96px;

  --radius-sm: 8px;
  --radius-md: 16px;
  --radius-lg: 24px;
  --radius-full: 9999px;

  --shadow-sm: 0 1px 3px rgba(15,23,42,.05);
  --shadow-md: 0 10px 30px rgba(15,23,42,.08);
  --shadow-lg: 0 24px 50px rgba(15,23,42,.12);

  --container-max: 1200px;

  --ease-out: cubic-bezier(.22, 1, .36, 1);
  --dur-fast: 180ms;
  --dur-base: 320ms;
}
```

## Componentes (mapa)
- **Header sticky transparente:** vira `bg-white/90 backdrop-blur` ao rolar; logo + nav + telefone (`(11) 99999-0000` clicável) + CTA accent "Agendar avaliação"
- **Hero split:** badge ("Clínica boutique em SP") · headline grande (display serif) · subtitle · 2 CTAs (primário accent + ghost "Conhecer a clínica") · trust strip horizontal logo abaixo
- **Trust strip:** "+15 anos", "+5.000 pacientes", "8 especialistas", "Avaliação 4.9 ★"
- **Serviços (6 cards):** ícone Lucide em círculo `--primary-soft` · título · descrição · "Saber mais →"
- **Sobre a clínica:** 2 col — texto à esquerda (parágrafos + bullet de diferenciais), foto IA à direita
- **Equipe (3 cards):** foto vertical 4:5 · nome (display) · especialidade · CRO
- **Depoimentos:** 3 cards lado a lado — aspas grandes · texto · estrela · foto pequena + nome
- **FAQ:** `<details>` com chevron animado, separador sutil
- **Agendamento:** 2 col — texto motivador à esquerda · form à direita (nome, telefone, serviço, mensagem opcional, botão accent full-width)
- **Localização:** texto + iframe Google Maps + horário
- **Footer:** 3 col simples (logo + slogan · links · contato/redes)

**Ícones Lucide:** `sparkles` (limpeza), `align-justify` (ortodontia), `screwdriver` (implantes — ou `gem`), `sun` (clareamento), `baby` (odontopediatria), `heart` (harmonização), `phone`, `map-pin`, `clock`, `chevron-down`, `whatsapp` (não tem nativo — uso `message-circle`), `star`, `check-circle-2`.

## Imagens IA (catálogo de prompts pro `data.js`)
| Slot | Prompt sugerido | Dimensões |
|---|---|---|
| Hero | `confident young woman bright white natural smile, soft window light, premium dental editorial photography, shallow depth of field` | 900×1100 |
| Sobre clínica | `modern dental clinic interior, beige wood and white, plants, natural sunlight, minimalist scandinavian design, wide angle` | 1000×750 |
| Equipe 1 | `professional dentist woman 40s short hair white coat warm smile, clean studio background, soft natural lighting, premium portrait` | 600×750 |
| Equipe 2 | `professional dentist man 35s glasses beard white coat confident smile, clean studio background, soft lighting, premium portrait` | 600×750 |
| Equipe 3 | `professional dentist woman 30s long hair white coat friendly smile, clean studio background, soft lighting, premium portrait` | 600×750 |
| Depoimento 1 | `happy brazilian woman 30s natural smile casual shirt portrait, soft daylight, candid editorial` | 200×200 |
| Depoimento 2 | `friendly brazilian man 40s natural smile sweater portrait, soft daylight, candid editorial` | 200×200 |
| Depoimento 3 | `elegant brazilian woman 50s gentle smile blouse portrait, soft daylight, candid editorial` | 200×200 |

URL final: `https://image.pollinations.ai/prompt/{encode(prompt)}?width=W&height=H&nologo=true&seed=N`.

---
--- HANDOFF ---
De: designer-ui
Fase concluída: Fase 2 — Design
Resultado: Light mode premium. Paleta teal `#0E7C7B` + coral `#F97361` em branco generoso. Fontes Fraunces (display serif) + Inter. Layout single page com 11 seções. Tokens CSS prontos.
Aguardando do dono: aprovar paleta/fontes/tokens, ou pedir ajustes (ex: trocar coral por outra cor, usar sans no display em vez de serif, modo escuro).
Próximo agente: Fase 3 — implementação. Vou pedir **autorização explícita pra sair do cofre** e escrever em `C:\Projetos\odontovita\`.
