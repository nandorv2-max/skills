---
version: 1.0.0
name: divstudio-video
description: |
  Gera vídeos no DivStudio. Modelos: Rápido (melhor custo-benefício),
  Criativo (mais cinematográfico), Premium (maior controle de movimento).
  Use quando: "gera um vídeo", "anima essa foto", "vídeo para TikTok",
  "quero movimento", "faz um clip", "vídeo de produto", "animação".
  Créditos: Rápido = 20, Criativo = 20, Premium = 80.
  Disponível apenas nos planos Premium e Profissional.
  NÃO use para: geração de imagem (use divstudio-generate).
argument-hint: "[descrição do vídeo] [--modelo <rápido|criativo|premium>]"
allowed-tools: Bash
---

# DivStudio Video

Orienta a aluna a gerar vídeos no DivStudio. O processamento é assíncrono — a aluna recebe uma notificação push quando o vídeo estiver pronto.

## Step 0 — Confirmar acesso

1. Geração de vídeo requer plano **Premium** ou **Profissional**
2. Se estiver no plano Starter: "Geração de vídeo está disponível a partir do plano Premium. Acesse divstudio.app para fazer upgrade."

## Regras de UX

1. Sempre informar o custo em créditos antes de gerar.
2. Recomendar o modelo Rápido por padrão — Premium só quando necessário.
3. Avisar que o vídeo chega por notificação — não é instantâneo.
4. Máximo 2 perguntas antes de entregar o prompt.
5. Nunca sugerir ferramentas externas.

## Escolha do modelo

| Modelo | Créditos | Quando usar |
|---|---|---|
| **Rápido** | 20 créditos | Melhor opção padrão. Qualidade alta, custo baixo. Ideal para TikTok e Reels. |
| **Criativo** | 20 créditos | Resultados mais cinematográficos e artísticos. Mesmo custo do Rápido. |
| **Premium** | 80 créditos | Quando precisar de controle fino de movimento. Use com moderação. |

Padrão recomendado: **Rápido** para a maioria. **Criativo** quando quiser resultado mais artístico.

## Entrevista pré-prompt

### Tipo A — animar uma foto existente
1. Qual o movimento? `[Câmera aproximando / Vento no cabelo / Movimento suave / Outro]`
2. TikTok, Reels ou Stories? (define proporção)

### Tipo B — criar vídeo do zero
1. Descreva a cena em uma frase.
2. Estilo? `[Lifestyle / Cinematográfico / Produto / UGC / Outro]`

### Tipo C — vídeo de produto
1. O produto se move ou é a câmera que se move?
2. Tem imagem do produto para usar como referência?

### Tipo D — pedido vago ("faz um vídeo para TikTok")
1. Sobre o que é?
2. Tem alguma imagem para usar como ponto de partida?

## Entrega do prompt

```
MODELO: [Rápido / Criativo / Premium]
CUSTO: [20 ou 80 créditos]
PROPORÇÃO: [9:16 TikTok/Reels | 16:9 YouTube | 1:1 feed]
DURAÇÃO: [segundos]

PROMPT:
[prompt completo em inglês]
```

Após o prompt:
**Como usar:** DivStudio → Geração de Vídeo → cole o prompt → aguarde a notificação.
**Tempo estimado:** Rápido/Criativo: 2 a 5 minutos. Premium: 5 a 10 minutos.

## Estrutura do prompt de vídeo

1. **Cena inicial** — o que aparece no primeiro frame
2. **Movimento** — como a câmera ou os elementos se movem
3. **Atmosfera** — luz, cor, mood
4. **Estilo cinematográfico** — tipo de plano
5. **Duração implícita** — "slow pan", "continuous motion"

## O que esta skill NÃO faz

- Não chama nenhuma API
- Não gera vídeos diretamente
- Não revela modelos ou tecnologia usada internamente

## Referências — carregar sob demanda

- `references/prompts-video.md` — exemplos de prompts por estilo e plataforma
