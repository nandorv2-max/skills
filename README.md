# DivStudio Skills

Skills de IA para geração de imagens e vídeos via DivStudio. Funciona com Claude Code, Cursor, Codex e outros agentes que carregam skills em Markdown.

## Instalação

```bash
npx skills add divstudio-app/skills
```

## Skills

| Skill | Invocar | Descrição |
|---|---|---|
| `divstudio-generate` | `/divstudio:generate` | Geração de imagem em todos os módulos do app: cenários, ensaios, troca de pessoa, composição, avatar, influencer virtual e mais. |
| `divstudio-video` | `/divstudio:video` | Geração de vídeo com Veo 3.1 Fast, Grok 3 Video e Kling AI Motion Control. |
| `divstudio-produto` | `/divstudio:produto` | Fotos profissionais de produto — studio, lifestyle, Pinterest, TikTok Shop, banner, com modelo e conceitual. |

## Referência rápida

| O que você quer | Skill |
|---|---|
| Me colocar em um cenário / fundo | `divstudio-generate` |
| Ensaio fotográfico profissional | `divstudio-generate` |
| Trocar pessoa de uma foto | `divstudio-generate` |
| Criar avatar ou influencer virtual | `divstudio-generate` |
| Vestir uma roupa em mim | `divstudio-generate` |
| Foto de produto para TikTok Shop | `divstudio-produto` |
| Foto de produto para Pinterest | `divstudio-produto` |
| Banner de produto para site | `divstudio-produto` |
| Gerar vídeo para TikTok | `divstudio-video` |
| Animar uma foto | `divstudio-video` |

## Como funciona

As skills são arquivos Markdown puros. Elas ensinam o agente a usar o DivStudio corretamente — qual módulo usar, como montar o prompt, quais potenciadores aplicar, e o que evitar. Nenhum código é executado localmente.

## Requisitos

- Conta ativa no DivStudio: divstudio.app
- Plano Premium ou Profissional para vídeo e modelos Ultra
- Plano Profissional para imagens ilimitadas

## Estrutura

```
skills/
├── CLAUDE.md                          # Regras globais para todos os agentes
├── README.md                          # Este arquivo
├── divstudio-generate/
│   ├── SKILL.md                       # Skill principal de imagem
│   └── references/
│       ├── modulos.md                 # Detalhes de cada módulo
│       ├── potenciadores.md           # Guia completo de potenciadores
│       ├── realismo.md                # Escala de calibração visual
│       └── erros-comuns.md            # Os 12 erros e como evitar
├── divstudio-video/
│   ├── SKILL.md                       # Skill principal de vídeo
│   └── references/
│       ├── modelos-video.md           # Comparação dos modelos
│       └── prompts-video.md           # Exemplos por estilo e plataforma
└── divstudio-produto/
    ├── SKILL.md                       # Skill principal de produto
    └── references/
        ├── modos-produto.md           # Exemplos por modo
        └── tiktok-shop.md             # Boas práticas para TikTok Shop
```

## Licença

MIT
