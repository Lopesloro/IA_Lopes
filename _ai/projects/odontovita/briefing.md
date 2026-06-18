# Briefing — OdontoVita

## Negócio
- **Nome:** OdontoVita
- **Ramo:** Clínica odontológica multi-especialidades
- **Objetivo nº1:** Institucional + captação de lead (agendamento de avaliação)
- **Público-alvo:** Adultos 25–55, classe B, que valorizam estética + confiança + ambiente acolhedor

## Conteúdo / escopo
- **Hero:** chamada forte + CTA "Agendar avaliação" + foto humana sorriso
- **Selo de confiança:** linha com 4 micro-indicadores (anos, pacientes, especialistas, CRO)
- **Serviços (6 cards):** Limpeza, Ortodontia (alinhadores invisíveis), Implantes, Clareamento, Odontopediatria, Harmonização Orofacial
- **Sobre a clínica:** 2–3 parágrafos + imagem do ambiente
- **Equipe (3 dentistas fictícios):** foto + nome + especialidade + CRO
- **Depoimentos (3):** texto + nome + foto
- **FAQ (5–6 perguntas):** acordeão
- **Agendamento:** formulário (nome, telefone, serviço, mensagem) → ao enviar, abre WhatsApp com mensagem pré-preenchida
- **Localização:** endereço fictício + horário + iframe do Google Maps (genérico) ou imagem-mapa
- **Header:** logo + nav âncora + telefone clicável + CTA "Agendar"
- **Footer:** institucional curto

## Identidade visual (premissas a confirmar pelo designer)
- Tom: **confiável, acolhedor, moderno** (não clínico-frio)
- Paleta: branco generoso + azul sereno + accent quente (a definir)
- Tipografia humana e legível
- Muita whitespace, fotos grandes, micro-animações ao scroll

## Imagens
- **Todas geradas por IA via Pollinations.ai** (free, embed via `<img src="https://image.pollinations.ai/prompt/...">`).
- Prompts catalogados em `_ai/projects/odontovita/imagens.md` (criar depois do design)
- Categorias: hero (sorriso aproximado), equipe (3 retratos), ambiente (sala de atendimento, recepção), depoimentos (3 retratos).

## Funcionalidade (sem backend)
- Formulário com validação client-side → redireciona pra WhatsApp (`https://wa.me/55XXXXXXXXXXX?text=...`)
- FAQ acordeão
- Smooth scroll para âncoras
- Animações GSAP ScrollTrigger nos blocos

## Não-escopo
- Backend / banco / e-mail real
- Área logada / agendamento real online (só lead via WhatsApp)
- Blog / CMS
- Multi-idioma

## A confirmar (placeholders pra demo)
- Logo: gerar versão tipográfica simples
- Telefone: `(11) 99999-0000` (placeholder)
- Endereço: `Av. Paulista, 1000 — São Paulo, SP` (placeholder)
- CROs e nomes da equipe: fictícios
- WhatsApp: número fictício, link pronto pra trocar depois

## Stack alvo
HTML/CSS/JS + Tailwind CDN + GSAP + Lucide (do `stack-padrao.md`).

## Pasta de saída
- Código: `C:\Projetos\odontovita\` (fora do cofre → autorização na Fase 3)
- Estado/decisões: `C:\Cofre\_ai\projects\odontovita\`

## Referências
- Padrões 2026: whitespace, fotos humanas grandes, paleta soft, CTA de agendamento dominante.
- Fontes: Colorlib, Delmain, Azuro (research da Fase 0).
