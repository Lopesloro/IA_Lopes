# Pipeline: /novosite (nível sênior)
> Conduzido pelo [[orquestrador]]. Recebe material bruto, entende, pesquisa, critica, planeja, e eu aprovo o blueprint antes de codar. Multipágina por padrão. Ver [[PROTOCOLO]] · [[PROTOCOLO-CRITICA]] · [[INDEX]].

## Como eu uso
Digito /novosite e jogo o material que tiver: descrição do cliente, URL do site atual, LinkedIn, fotos, links, redes. Não preciso organizar — a IA entende.

## ETAPA 1 — Entender (sem me cobrar organização)
[[analista-entrada]] processa TODO o material → entrada.md (ramo, identidade visual com hex, objetivo, público, requisitos, lacunas).

## ETAPA 2 — Pesquisar
[[pesquisador]] estuda o negócio e o mercado (ferramentas grátis) → pesquisa.md (o que a empresa faz, concorrentes, o que converte no setor, oportunidade).

## ETAPA 3 — Estratégia
[[estrategista]] define a mensagem nº1, o CTA dominante, a jornada e as provas necessárias → estrategia.md. Foco em primeira impressão e conversão.

## ETAPA 4 — Críticar e perguntar o essencial
Os agentes (modo [[PROTOCOLO-CRITICA]]) apontam lacunas. [[briefing-cliente]] me faz só as perguntas que faltam (poucas, objetivas).

## ETAPA 5 — BLUEPRINT (eu aprovo aqui)
Montar UM blueprint completo em _ai/projects/<slug>/blueprint.md:
- Mapa de páginas (multipágina) e navegação
- Estrutura seção a seção de cada página
- Fluxos de clique (card → página de detalhe)
- Design: consultar [[design-intelligence]] (ui-ux-pro-max) + identidade do cliente → paleta hex, tipografia, espaçamento generoso, tokens :root
- Mídia: [[midia-hero]] decide vídeo ou imagem + fontes grátis
- Stack: [[arquiteto-frontend]] (front) + [[arquiteto-backend]] (front vs fullstack + o que falta)
- Conteúdo: tom (sem lorem ipsum)
MOSTRAR o blueprint inteiro e PARAR. Eu aprovo UMA vez.

## ETAPA 6 — Implementar (após aprovação)
Codar o site inteiro seguindo o blueprint, em C:\Projetos\<slug> (fora de _ai/ → pedir aprovação pra escrever fora). Frontend + backend conforme decidido. Mídia com fallback.

## ETAPA 7 — Auditar e entregar
[[auditor-performance]] roda checklist (Lighthouse ≥90, LCP/CLS/INP, SEO, acessibilidade, responsivo). Entrega + como ver no navegador + deploy.

## REGRAS DE OURO
- Multipágina por padrão (landing só se pedido).
- Blueprint aprovado por mim antes de qualquer código.
- Espaçamento generoso (nunca compacto). Nível Awwwards.
- Primeira impressão vende o negócio do cliente.
- Só ferramentas grátis. Nada de copiar conteúdo de terceiros — só estrutura.
