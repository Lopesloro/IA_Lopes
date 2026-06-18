# Briefing — TurboShop

## Negócio
- **Nome:** TurboShop
- **Ramo:** E-commerce demo (eletrônicos e acessórios genéricos)
- **Objetivo:** Site funcional para testar o pipeline `/novosite` ponta-a-ponta
- **Público:** N/A (demo interna)

## Escopo funcional (mínimo viável para "testar")
- Home com hero + vitrine de produtos (8–12 itens)
- Card de produto: imagem, nome, preço, botão "Adicionar"
- Carrinho lateral funcional (abre/fecha, soma/remove itens, total)
- Persistência do carrinho no `localStorage`
- Página/seção de detalhes do produto (modal ou rota simples)
- Header com logo + ícone do carrinho + contador
- Footer institucional

## Não-escopo
- Checkout real / gateway de pagamento
- Backend / banco de dados
- Autenticação / contas

## Restrições
- Sem build complexo: HTML/CSS/JS puro + Tailwind via CDN
- Imagens via Unsplash (URLs públicas)
- Tudo em um único projeto estático que abre direto no navegador

## Referências visuais
- Aesthetic moderno tipo Apple/Linear: clean, contraste forte, micro-animações
- Paleta a ser definida pelo designer (sugestão: dark mode com accent vibrante)

## Pasta de saída
- Código: `C:\Projetos\turboshop\` (fora do cofre — requer aprovação na Fase 3)
- Estado/decisões: `C:\Cofre\_ai\projects\turboshop\`
