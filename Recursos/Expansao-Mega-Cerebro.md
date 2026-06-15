# 🧠⚡ Expansão MEGA CÉREBRO — O que falta pra escalar de verdade

> Atualizado junho/2026. Coloque em `Recursos/`.
> Hoje você tem: estrutura PARA + _ai/ + agentes + skills + Arsenal.
> Isto adiciona as CAMADAS que faltam pra virar um sistema vivo e automatizado.
> Lê de cima pra baixo: cada camada multiplica a anterior.

---

## MAPA DAS CAMADAS (o que você tem vs o que falta)

```
[VOCÊ TEM]  Estrutura + Agentes + Skills + Arsenal
              ↓ falta conectar com o mundo
[CAMADA 1]  MCPs — dar braços ao Claude Code (GitHub, browser, DB, docs)
[CAMADA 2]  Plugins Obsidian — transformar o cofre num painel vivo
[CAMADA 3]  Comandos compostos — workflows de 1 linha que cruzam tudo
[CAMADA 4]  Dashboards — ver o estado de tudo num lugar só
[CAMADA 5]  Automação — coisas que rodam sem você
[CAMADA 6]  Memória semântica — o cofre "se lembra" sozinho
[CAMADA 7]  Pipeline de conteúdo — virar autoridade (TikTok/Insta)
[CAMADA 8]  Governança — manutenção que impede virar lixo
```

---

## CAMADA 1 — MCPs (a maior peça que falta)

MCP = Model Context Protocol. Dá ao Claude Code "braços" pra agir em sistemas externos com SUAS credenciais. Hoje seu Claude Code só mexe em arquivos; com MCP ele abre PR no GitHub, testa site no navegador, consulta banco, lê doc atualizada. **Isto é o maior salto disponível.**

| MCP | O que faz | Por que VOCÊ precisa |
|---|---|---|
| **GitHub MCP** (oficial) | Lê/cria issues, PRs, busca em repos, automatiza | Você versiona tudo no GitHub; Claude vira contribuidor autônomo |
| **Context7** | Injeta doc ATUAL de libs (sem alucinar API) | Para de inventar sintaxe de React/Next/Tailwind — o de maior impacto |
| **Playwright MCP** (Microsoft) | Controla navegador: clica, preenche, screenshot, teste E2E | Testa visualmente os sites que você entrega; valida antes do cliente ver |
| **Supabase MCP** | Conversa com seu Supabase em linguagem natural | Quando o site virar app com banco/login |
| **Postgres MCP** | Query direto no Postgres | Seu stack de backend |
| **Figma MCP** (oficial) | Lê design do Figma e gera código fiel | Se receber layout em Figma do cliente |
| **Brave Search MCP** | Busca web em tempo real dentro do Claude Code | Pesquisa de mercado/preço sem sair do terminal |

### ⚠️ Regra de ouro dos MCPs
Não instale todos. Acima de ~40-50 ferramentas ativas o modelo começa a errar qual usar (cada MCP expõe 5-25 ferramentas; GitHub sozinho são ~20, Playwright ~25). **Instale 4 a 6.** Pro seu perfil, comece com: **GitHub + Context7 + Playwright**. Adicione Supabase/Postgres quando pegar projeto com banco.

### Como instalar (exemplo)
No terminal: `claude mcp add` (ver doc oficial em docs.claude.com). A config fica em `~/.claude/settings.json` e vale pra todos os projetos.
Cada MCP roda código na sua máquina com suas credenciais — só instale os de fonte oficial/confiável.

---

## CAMADA 2 — Plugins do Obsidian (cofre vivo)

Seu cofre hoje é texto parado. Estes plugins transformam ele num painel. Instale por: Configurações → Plugins da comunidade → Procurar.

| Plugin | O que faz | Uso no seu sistema |
|---|---|---|
| **Dataview** | Trata o cofre como banco de dados; cria tabelas/listas dinâmicas via query | Dashboard de projetos, agentes, leads — atualiza sozinho |
| **Templater** | Templates com lógica (data, prompts, scripts) | Nota de projeto/proposta/cliente preenchida automaticamente |
| **Obsidian Git** | Versiona o cofre no Git automático | RESOLVE o problema da memória entre sessões; backup + histórico |
| **QuickAdd** | Captura rápida + macros (1 botão faz N ações) | Criar projeto novo já com estrutura, abrir agente, etc. |
| **Kanban** | Quadros visuais | Pipeline de clientes/projetos arrastando cartões |
| **Calendar + Periodic Notes** | Notas diárias/semanais com data | Log diário, revisão semanal de manutenção |
| **Tasks** | Sistema de tarefas com query | Pendências dos projetos num lugar |
| **Smart Connections** | IA acha notas semanticamente parecidas (embeddings) | "que notas se conectam com isso?" sem você linkar tudo na mão |
| **Tag Wrangler** | Renomeia/funde tags em massa | Evita bagunça de tag (#projeto vs #projetos) |
| **Omnisearch** | Busca que "só funciona" | Achar qualquer coisa no cofre grande |
| **Excalidraw** | Desenho/diagrama dentro do cofre | Esboçar arquitetura de site, wireframe |
| **Homepage** | Define uma nota como painel inicial | Sua central de comando ao abrir o Obsidian |

**Combo mínimo poderoso:** Dataview + Templater + Obsidian Git + QuickAdd + Smart Connections.
**Cuidado:** acima de 40 plugins o Obsidian fica lento. Audite a cada 3 meses, desative o que não usa.

---

## CAMADA 3 — Comandos compostos (workflows de 1 linha)

Você já tem `/novosite`. O poder real é criar mais comandos que cruzam MCPs + agentes. Crie como skills em `_ai/skills/`. Exemplos pro seu trabalho:

| Comando | O que dispara |
|---|---|
| `/novosite` | Pipeline completo de site (já tem) |
| `/proposta <cliente>` | briefing-cliente → arquiteto (dimensiona) → proposta-comercial → PDF |
| `/auditar <url>` | Playwright abre o site → auditor-performance → relatório |
| `/deploy <projeto>` | revisor-codigo → build → push GitHub → instruções deploy |
| `/prospectar <nicho> <cidade>` | Brave Search acha negócios → qualifica → grava em clientes.md |
| `/revisar-pr <link>` | GitHub MCP puxa o PR → revisor-codigo comenta |
| `/estudar <tema>` | bibliotecario acha o que você já tem → tutor-algoritmos monta trilha |

Cada comando é um `.md` descrevendo os passos (como o PIPELINE-novosite). É isso que torna o Claude Code diferente: automação composta, reutilizável.

---

## CAMADA 4 — Dashboards com Dataview

Com Dataview instalado, crie notas-painel que se atualizam sozinhas. Coloque em `Areas/Dashboards/`. Exemplos de query (vão dentro de bloco ```dataview):

**Projetos ativos:**
```
TABLE status, fase, prazo FROM "_ai/projects" WHERE status != "concluído" SORT prazo ASC
```

**Leads a contatar:**
```
TABLE contato, projeto, status FROM "_ai/briefings" WHERE contains(file.name, "cliente")
```

**Decisões técnicas recentes:**
```
LIST FROM "_ai/decisions" SORT file.ctime DESC LIMIT 10
```

Pra isso funcionar, suas notas precisam de metadados (frontmatter `--- status: ativo ---`). O Templater preenche isso automático.

---

## CAMADA 5 — Automação (roda sem você)

| Ferramenta | O que automatiza | Conexão |
|---|---|---|
| **Obsidian Git (auto-commit)** | Salva e versiona o cofre a cada X min | Backup + memória sem esforço |
| **GitHub Actions** | CI/CD: testa e faz deploy ao dar push | Seus sites publicam sozinhos |
| **n8n / Make / Zapier** | Conecta apps (form do site → planilha → e-mail) | Captura de lead dos sites de cliente |
| **Cron / Agendador do Windows** | Roda script do Claude Code em horário fixo | Ex: relatório semanal de projetos toda sexta |
| **QuickAdd macros** | 1 clique = várias ações no Obsidian | Capturar ideia, criar projeto |

---

## CAMADA 6 — Memória semântica

O Claude Code não tem memória entre sessões — você resolve isso com camadas de arquivo + busca semântica:

- **Smart Connections** (plugin): embeddings locais; pergunta "o que se conecta com X" e ele acha notas relacionadas sem links manuais.
- **Logs estruturados** em `_ai/logs/` (você já tem): a memória manual. Mantenha disciplina de gravar fim de sessão.
- **briefings/** sempre atualizado: o "estado permanente" que a IA puxa.
- Quando a IA resolver memória de vez (a provocação do vídeo), quem tiver sistema e utilidade — você — sai na frente.

---

## CAMADA 7 — Pipeline de conteúdo (vira autoridade)

Você tem interesse em TikTok Shop/Insta/afiliados. O cofre pode virar máquina de conteúdo:

| Peça | Ferramenta | Fluxo |
|---|---|---|
| Ideias | nota em `00_Inbox` + Smart Connections | captura solta → conecta |
| Roteiro | agente novo `roteirista` + briefings | tema → roteiro estruturado |
| Vídeo programático | **Remotion** (já no Arsenal) | dados → vídeo renderizado |
| Thumbnail/arte | Canva / Recraft / Figma | gerar em lote |
| Agendamento | Metricool / Buffer | postar em horário |
| Métricas | planilha + Dataview | o que performou volta pro Inbox |

Sugiro criar um agente `roteirista` e um `/conteudo <tema>` na Camada 3.

---

## CAMADA 8 — Governança (impede virar lixo)

A parte que o vídeo mais enfatiza e quase ninguém faz. Sem isto, mega cérebro vira depósito morto.

- **Rotina de poda** (mensal): agente [[bibliotecario]] lista órfãos/duplicados → você decide.
- **Revisão de outputs**: nada gerado por IA é "verdade" até você revisar.
- **Audit de plugins/MCPs** (trimestral): desativa o que não usou.
- **ADRs em decisions/**: registra por que decidiu cada coisa — não rediscute.
- **Nota de manutenção** semanal (Periodic Notes): 10 min revisando o sistema.

---

## ORDEM DE IMPLEMENTAÇÃO SUGERIDA (não faça tudo de uma vez)

1. **Semana 1:** Obsidian Git + Dataview + Templater (cofre vivo e seguro).
2. **Semana 2:** GitHub MCP + Context7 + Playwright (Claude Code ganha braços).
3. **Semana 3:** 2-3 comandos compostos (`/proposta`, `/auditar`).
4. **Semana 4:** 1 dashboard de projetos + QuickAdd.
5. **Depois:** automação (GitHub Actions, auto-commit), conteúdo, governança.

Cada camada multiplica. Não pula a governança — é o que separa mega cérebro de depósito de lixo.
