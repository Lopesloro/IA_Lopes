# Skill: Novo App Next.js
> Versão profissional. FASE 3 quando o projeto é app. Ver [[INDEX]] · [[PROTOCOLO]].

## Stack e por quê
Next.js 16 App Router (SSR+SEO) · TypeScript strict · Tailwind v4 · shadcn/ui (você é dono do código) · Zustand (estado simples) · TanStack Query (cache de API) · React Hook Form + Zod (forms type-safe) · Supabase OU Express+Postgres · deploy Vercel.

## Processo
1. `npx create-next-app@latest` (TS, Tailwind, App Router, ESLint).
2. `npx shadcn@latest init` + add button card form dialog table sonner.
3. Pastas: app/ components/ui components/ lib/ hooks/ types/ + alias @/.
4. ESLint + Prettier. Tema dark/light (shadcn).
5. Camadas: Zustand (UI state) · TanStack Query (server state) · RHF+Zod (forms).
6. Auth/banco: perguntar (Clerk/Supabase/Auth.js).

## EXEMPLO — validação Zod reaproveitável (front + back)
```ts
import { z } from "zod";
export const leadSchema = z.object({
  nome: z.string().min(2, "Nome muito curto"),
  email: z.string().email("E-mail inválido"),
  telefone: z.string().min(10).optional(),
});
export type Lead = z.infer<typeof leadSchema>;
```

## ANTI-PADRÕES
- ❌ Commitar .env (secrets). Use .env.local + .gitignore.
- ❌ Input sem validação Zod.
- ❌ useEffect pra buscar dados (use TanStack Query).
- ❌ Estado global pra tudo (server state ≠ UI state).
- ❌ `any` no TypeScript.
- ❌ Componente gigante de 400 linhas — quebrar.

## Checklist
- [ ] TS strict, zero `any` · [ ] .env.local fora do Git · [ ] Zod em todo input
- [ ] loading + error + empty states · [ ] responsivo · [ ] Lighthouse ≥ 90
