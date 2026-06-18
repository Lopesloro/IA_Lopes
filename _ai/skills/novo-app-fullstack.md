# Skill: App Fullstack
> Para projetos com login, dados dinâmicos, painel, carrinho. Usada na ETAPA 3. Ver [[INDEX]] · [[PROTOCOLO]].
## Stack
Frontend: Next.js 16 + TS + Tailwind + shadcn/ui. Backend: Node/Express OU rotas Next + Postgres (ou Supabase). Auth: Clerk/Supabase/Auth.js. Validação Zod ponta a ponta.
## Estrutura
app/ (rotas e páginas) · components/ · lib/ (db, auth) · api/rotas · types/ · prisma ou drizzle (schema).
## Processo
1. Modelar dados (tabelas/relações) conforme o blueprint.
2. Criar rotas/API com validação Zod.
3. Páginas multipágina (cada recurso sua rota).
4. Auth se o blueprint pedir.
5. Estados loading/error/empty.
## ANTI-PADRÕES
❌ .env no Git ❌ input sem validação ❌ any no TS ❌ tudo num componente ❌ landing single-page quando pediram multipágina.
## Checklist
- [ ] Multipágina/rotas - [ ] Backend funcional - [ ] Zod - [ ] auth (se pedido) - [ ] responsivo - [ ] Lighthouse ≥90
