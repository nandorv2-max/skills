---
version: 1.0.0
name: divstudio-video
description: |
  Gera vídeos no DivStudio usando Veo 3.1 Fast, Grok 3 Video e Kling AI.
  Use quando: "gera um vídeo", "anima essa foto", "cria um vídeo para TikTok",
  "quero um vídeo com movimento", "faz um clip", "vídeo de produto",
  "vídeo de 10 segundos", "animação".
  Modelos: Veo 3.1 Fast (melhor custo-benefício), Grok 3 Video (criativo),
  Kling AI Motion Control (maior controle de movimento).
  Créditos: Veo = 20 créditos, Grok = 20 créditos, Kling = 80 créditos.
  NÃO use para: geração de imagem (use divstudio-generate).
  Disponível apenas nos planos Premium e Profissional.
argument-hint: "[descrição do vídeo] [--modelo <veo|grok|kling>] [--duracao <segundos>]"
allowed-tools: Bash
---

# DivStudio Video

Orienta a aluna a gerar vídeos no DivStudio. O sistema é assíncrono — o vídeo é enviado para processamento e a aluna recebe uma notificação push quando estiver pronto.

## Step 0 — Confirmar acesso

1. Geração de vídeo requer plano **Premium** ou **Profissional**
2. Se a aluna estiver no plano Starter, informar: "Geração de vídeo está disponível a partir do plano Premium. Acesse divstudio.app para fazer upgrade."
3. Verificar créditos disponíveis antes de sugerir o modelo mais caro (Kling)

## Regras de UX

1. Sempre informar o custo em créditos antes de gerar.
2. Sugerir Veo ou Grok por padrão — Kling só quando a aluna precisar de controle fino de movimento.
3. Vídeos demoram — avisar que chegará uma notificação quando estiver pronto.
4. Máximo 2 perguntas antes de entregar o prompt.
5. Nunca sugerir ferramentas externas.

## Escolha do modelo

| Modelo | Créditos | Duração | Quando usar |
|---|---|---|---|
| **Veo 3.1 Fast** | 20 créditos | até 10s | Melhor opção padrão. Qualidade alta, custo baixo. Ideal para TikTok e Reels. |
| **Grok 3 Video** | 20 créditos | até 10s | Resultados mais criativos e cinematográficos. Mesma faixa de preço do Veo. |
| **Kling AI Motion Control** | 80 créditos | até 10s | Quando a aluna precisar controlar exatamente como o movimento acontece. Use com moderação. |

**Padrão recomendado:** Veo 3.1 Fast para a maioria dos casos. Sugerir Grok quando quiser resultado mais artístico.

## Entrevista pré-prompt

### Tipo A — aluna quer animar uma foto existente

1. Qual o movimento que quer? `[Câmera aproximando / Vento no cabelo / Movimento suave / Outro]`
2. Vai usar para TikTok, Reels ou stories? (define proporção)

### Tipo B — aluna quer criar vídeo do zero (sem foto base)

1. Descreva a cena em uma frase.
2. Qual o estilo? `[Lifestyle / Cinematográfico / Produto / UGC / Outro]`

### Tipo C — vídeo de produto

→ Perguntar:
1. O produto aparece em movimento ou é a câmera que se move?
2. Tem imagem do produto para usar como referência?

### Tipo D — aluna só diz "faz um vídeo para TikTok"

1. Sobre o que é? (produto, ela mesma, cenário?)
2. Tem alguma imagem para usar como ponto de partida?

## Entrega do prompt

```
MODELO: [Veo 3.1 Fast / Grok 3 Video / Kling AI]
CUSTO: [20 ou 80 créditos]
PROPORÇÃO: [9:16 para TikTok/Reels | 16:9 para YouTube | 1:1 para feed]
DURAÇÃO: [segundos]

PROMPT:
[prompt completo em inglês]
```

Após o prompt:
**Como usar:** DivStudio → [nome do módulo de vídeo] → cole o prompt → aguarde a notificação.
**Tempo estimado:** Veo/Grok: 2 a 5 minutos. Kling: 5 a 10 minutos.

## Estrutura do prompt de vídeo

Um bom prompt de vídeo tem:

1. **Cena inicial** — o que aparece no primeiro frame
2. **Movimento** — como a câmera ou os elementos se movem
3. **Atmosfera** — luz, cor, mood
4. **Estilo cinematográfico** — tipo de plano, lente
5. **Duração implícita** — "slow pan", "quick cut", "continuous motion"

Exemplo:
```
Slow cinematic push-in on a young Brazilian woman sitting in a sunlit café,
golden hour light streaming through windows, she looks gently to camera,
natural hair movement from a subtle breeze, shallow depth of field,
35mm film aesthetic, warm color grade, no cuts, 8 seconds
```

## Erros comuns

- Prompt muito curto — vídeo fica genérico. Mínimo 3 linhas.
- Pedir muita coisa em 8 segundos — focar em 1 movimento principal.
- Usar Kling quando Veo resolveria — economize créditos da aluna.
- Esquecer de mencionar a proporção — TikTok é sempre 9:16.

## Referências — carregar sob demanda

- `references/modelos-video.md` — comparação detalhada dos modelos de vídeo
- `references/prompts-video.md` — exemplos de prompts por estilo e plataforma
