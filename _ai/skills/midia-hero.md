# Skill: Mídia do Hero e Seções
> Vídeo/imagem integrados, fontes grátis, coerentes com o negócio. Usada pelo [[designer-ui]]. Ver [[INDEX]] · [[PROTOCOLO]].

## Decisão: vídeo ou imagem
- **Vídeo de fundo no hero** → quando o negócio se beneficia de movimento/impacto (indústria, energia, esporte, gastronomia, construção). Mostra a operação real.
- **Imagem de alta qualidade** → quando leveza e clareza importam mais (advocacia, consultoria, saúde, serviços B2B sóbrios).
Justificar a escolha pelo setor (puxar de estrategia.md e pesquisa.md).

## Fontes GRÁTIS
- Imagens: Unsplash, Pexels, Pixabay (URL direta ou download).
- Vídeo: Pexels Videos, Coverr, Mixkit (grátis, uso comercial — conferir licença de cada clip).
- Otimização: Squoosh (imagem), HandBrake (vídeo).

## Boas práticas de vídeo no hero (não travar)
```html
<video class="hero__bg" autoplay muted loop playsinline poster="fallback.jpg">
  <source src="hero.webm" type="video/webm">
  <source src="hero.mp4" type="video/mp4">
</video>
```
- SEMPRE muted + playsinline (senão não dá autoplay no mobile).
- poster = imagem de fallback (aparece enquanto carrega).
- Vídeo curto (8-15s), leve (<3MB), comprimido. Em mobile, considerar trocar por imagem (media query) pra não pesar.
- overlay escuro por cima pra o texto ler bem.

## ANTI-PADRÕES
- ❌ Vídeo com som automático.
- ❌ Vídeo pesado (>5MB) sem fallback.
- ❌ Imagem "cara de banco de imagem genérico" / "cara de IA" que não tem a ver com o negócio.
- ❌ Texto do hero ilegível sobre a mídia (sempre overlay/contraste).
- ❌ Autoplay sem poster (tela em branco enquanto carrega).

## Saída
Recomendação de mídia no blueprint +, na implementação, o HTML/CSS pronto com fallback.
