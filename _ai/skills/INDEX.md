# 📋 Lista Mestra de Skills — Segundo Cérebro

> Skills = arquivos de instrução que o Claude Code executa quando você pede ("use a skill X").
> Os agentes as chamam dentro dos pipelines. Ficam em `_ai/skills/`.
> Esta é a visão geral; o conteúdo de cada uma está nos blocos de instalação.

## WEB DEV (núcleo do seu trabalho)
| Skill | O que faz | Agente que usa |
|---|---|---|
| novo-site-institucional | Scaffolding de site HTML/CSS/JS puro | arquiteto-frontend |
| novo-app-next | Setup app Next.js + shadcn + stack | arquiteto-frontend |
| landing-astro | Landing/conteúdo com Astro + SEO | arquiteto-frontend |
| auditar-performance | Checklist perf/SEO/acessibilidade | auditor-performance |
| componente-animado | Cria componente animado (GSAP/Motion) | designer-ui |
| design-tokens | Gera paleta + tipografia + tokens CSS | designer-ui |
| seo-onpage | Otimiza SEO on-page de uma página | auditor-performance |
| deploy-checklist | Passo a passo de publicação | auditor-performance |
| revisar-codigo | Revisão estruturada de código | revisor-codigo |
| responsivo-fix | Audita e corrige responsividade | revisor-codigo |

## NEGÓCIO / FREELANCE
| Skill | O que faz | Agente que usa |
|---|---|---|
| proposta-cliente | Monta proposta técnica+comercial | proposta-comercial |
| prospectar-leads | Acha e qualifica clientes | prospector-clientes |
| mensagem-cliente | Redige 1ª abordagem/follow-up | prospector-clientes |
| escopo-projeto | Quebra projeto em tarefas+prazo | gestor-projeto |
| status-semanal | Relatório de status dos projetos | gestor-projeto |

## ACADÊMICO (PUC)
| Skill | O que faz | Agente que usa |
|---|---|---|
| trilha-estudo | Monta trilha de aprendizado de um tema | tutor-algoritmos |
| explicar-algoritmo | Explica algoritmo + Big-O + exemplo | tutor-algoritmos |
| revisar-texto-academico | Revisa texto PT-BR (norma/ABNT) | revisor-academico |
| resumo-aula | Estrutura material de estudo SEU | bibliotecario (organiza) |

## ORGANIZAÇÃO / SISTEMA
| Skill | O que faz | Agente que usa |
|---|---|---|
| novo-projeto | Cria pasta+estado de projeto novo | orquestrador |
| manutencao-cofre | Lista órfãos/duplicados pra podar | bibliotecario |
| log-sessao | Grava log de fim de sessão | qualquer agente |
| conectar-notas | Sugere links faltantes entre notas | bibliotecario |

## CONTEÚDO (TikTok/Insta — opcional)
| Skill | O que faz | Agente que usa |
|---|---|---|
| roteiro-video | Roteiro estruturado de vídeo curto | (roteirista, se criar) |
| ideias-conteudo | Gera pautas a partir do Inbox | bibliotecario |
