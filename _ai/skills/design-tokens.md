# Skill: Design Tokens
> Versão profissional. FASE 2 do [[PIPELINE-novosite]], pelo [[designer-ui]]. Ver [[INDEX]] · [[PROTOCOLO]].

## Objetivo
Entregar a identidade visual como TOKENS prontos pro código — não descrição vaga tipo "cores modernas". O dev (ou a skill de site) copia e usa.

## Como decidir (não chutar)
1. **Tom:** 3 adjetivos tirados do briefing do cliente (ex: "industrial, confiável, direto"). Tudo decorre disso.
2. **Cor:** paleta enxuta. 1 cor de destaque (accent) que marca SÓ CTAs e links — o resto é neutro. Referência de nível: sites premiados usam preto/branco/cinza + UMA cor viva. Gerar escala de neutros 50→900. Conferir contraste AA (4.5:1 texto normal, 3:1 grande).
3. **Tipografia:** 1 fonte de display (títulos) + 1 de corpo. Fontshare tem ótimas grátis (Clash Display, General Sans, Satoshi). Escala modular (1.25 major third). Pesos: display 500-700, corpo 400-500.
4. **Espaçamento:** escala base 8px (0.5/1/2/4/8rem). Consistência > variedade.
5. **Raio, sombra, motion:** UM raio padrão, sombras sutis, durações 0.3-0.6s ease-out.

## EXEMPLO de saída (design.md)
```
## Tom: industrial · confiável · direto
## Cor
--bg:#0c0c0e --surface:#16161a --text:#f4f4f5 --muted:#a1a1aa
--accent:#ff5a1f (CTAs/links apenas) --accent-hover:#ff7847
--success:#22c55e --error:#ef4444
Contraste verificado: text/bg = 16:1 ✓ · muted/bg = 6.2:1 ✓
## Tipografia
Display: Clash Display (700/500) · Corpo: Inter (400/500)
Escala: .8 / 1 / 1.25 / 1.56 / 1.95 / 2.44 / clamp(2.5,6vw,4.5)rem
## Espaçamento: .5 / 1 / 2 / 4 / 8 rem (base 8)
## Raio: 14px · Sombra: 0 4px 24px rgba(0,0,0,.12) · Motion: .4s power2.out
```

## ANTI-PADRÕES
- ❌ "Use cores que combinem" — sem hex, é inútil.
- ❌ Paleta com 5 cores fortes competindo.
- ❌ Accent usada em tudo (perde a função de destaque).
- ❌ Não verificar contraste.

## Sucesso
design.md tem TODOS os hex, escala tipográfica e bloco :root copiável. Handoff pra FASE 3.
