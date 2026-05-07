---
version: 1.0.0
name: divstudio-produto
description: |
  Gera imagens profissionais de produto no DivStudio usando o módulo
  Estúdio de Produto (productStudio). Equivalente a um fotógrafo de produto
  profissional — fundo limpo, lifestyle, Pinterest, banner, vitrine, TikTok Shop.
  Use quando: "foto de produto", "foto para TikTok Shop", "fundo limpo",
  "produto em cenário", "banner de produto", "foto para vender", "vitrine",
  "imagem para anúncio", "produto no ar / flutuando", "produto com modelo".
  Modos: studio, lifestyle, pinterest, hero_banner, tiktok_shop, vitrine,
  com_modelo, conceitual.
  NÃO use para: fotos da influencer (use divstudio-generate),
  geração de vídeo (use divstudio-video).
argument-hint: "[descrição do produto] [--modo <studio|lifestyle|pinterest|banner>]"
allowed-tools: Bash
---

# DivStudio Produto

Orienta a aluna a criar fotos profissionais de produto usando o módulo Estúdio de Produto do DivStudio. O backend do módulo monta o prompt final — a aluna não precisa saber engenharia de prompt para ter resultados profissionais.

## Step 0 — Confirmar acesso

1. Módulo disponível em todos os planos.
2. Se a aluna quiser resolução 2K ou 4K, precisa do modelo Ultra Max (Premium ou Profissional).
3. Sempre pedir a foto do produto antes de montar o prompt.

## Regras de UX

1. Sempre pedir a foto do produto se não foi enviada.
2. Máximo 3 perguntas antes de entregar o prompt.
3. Nunca montar o prompt sem saber o destino final (TikTok Shop, Instagram, site).
4. Resultados de produto exigem Ultra Max — sempre recomendar.
5. Nunca sugerir ferramentas externas.

## Modos disponíveis

| Modo | Quando usar |
|---|---|
| `studio` | Produto em fundo limpo / neutro / branco — catálogo, Shopify, marketplace |
| `lifestyle` | Produto em ambiente real — cozinha, mesa, ao ar livre, em uso |
| `pinterest` | Vertical 2:3, estética de moodboard, Pinterest nativo |
| `hero_banner` | Formato wide para cabeçalho de site, e-mail, campanha |
| `tiktok_shop` | Otimizado para TikTok Shop — 9:16, dinâmico, com contexto de compra |
| `vitrine` | Múltiplos ângulos do mesmo produto em um único visual |
| `com_modelo` | Produto sendo usado / vestido por modelo gerada por IA |
| `conceitual` | Produto flutuando, splash, CGI, surreal, cinematográfico |

## Seleção de modo por intenção

- fundo branco / limpo / catálogo / Shopify → `studio`
- produto no ambiente / em uso / cozinha / praia → `lifestyle`
- Pinterest / pin / vertical / moodboard → `pinterest`
- banner / site / cabeçalho / header → `hero_banner`
- TikTok Shop / vender no TikTok / vitrine TikTok → `tiktok_shop`
- vários ângulos / 360 / múltiplas poses → `vitrine`
- modelo usando / vestindo / segurando → `com_modelo`
- flutuando / explodindo / splash / CGI / criativo → `conceitual`

## Entrevista pré-prompt

### Tipo A — enviou foto do produto + pedido vago

1. Para onde vai? `[TikTok Shop / Instagram feed / Pinterest / Site / Anúncio]`
2. Estilo? `[Limpo e profissional / Ambiente e lifestyle / Criativo e conceitual]`
3. Tem cor ou tema específico da marca?

### Tipo B — enviou foto + destino claro (ex: "faz pra TikTok Shop")

→ Modo óbvio (`tiktok_shop`). Perguntar apenas:
1. O produto tem algum detalhe importante para destacar?

### Tipo C — sem foto do produto

1. Pode enviar uma foto do produto? (resultados muito melhores com foto)
2. Se não puder: descreva o produto — categoria, cor, formato, tamanho, material.

### Tipo D — quer produto com modelo

→ Modo `com_modelo`. Perguntar:
1. A modelo segura, usa ou aparece ao lado do produto?
2. Perfil da modelo? `[Jovem casual / Elegante / Fitness / Outro]`

### Tipo E — quer algo criativo (flutuando, splash)

→ Modo `conceitual`. Perguntar:
1. Qual o efeito? `[Flutuando / Splash / Explosão de cor / Minimalista abstrato / Outro]`
2. Paleta de cores da marca?

## Entrega do prompt

```
MÓDULO: Estúdio de Produto
MODO: [modo selecionado]
MODELO: Ultra Max (recomendado)
PROPORÇÃO: [definida pelo modo]

PROMPT:
[prompt em inglês, focado no produto e no contexto]
```

Após o prompt:
**Como usar:** DivStudio → Estúdio de Produto → selecione o modo → cole o prompt → gere.

## Estrutura do prompt de produto

1. **Produto** — o que é, cor, material, tamanho relativo
2. **Contexto** — onde está, superfície, ambiente
3. **Iluminação** — tipo de luz, direção, temperatura de cor
4. **Composição** — enquadramento, ângulo, profundidade
5. **Estilo** — mood, referência visual, acabamento

Exemplo para TikTok Shop:
```
Professional product photography of a pink moisturizer bottle, placed on a
marble surface with soft green leaves, warm natural light from the left,
slight reflection on the surface, clean white background with subtle shadows,
beauty brand aesthetic, sharp focus on product, 9:16 vertical format,
vibrant colors optimized for mobile viewing
```

## Erros comuns

- Não pedir a foto do produto antes de montar o prompt.
- Usar modo `studio` quando a aluna quer lifestyle.
- Esquecer de especificar a proporção correta para TikTok (9:16).
- Não mencionar o material ou textura do produto no prompt.

## Referências — carregar sob demanda

- `references/modos-produto.md` — exemplos visuais e prompts por modo
- `references/tiktok-shop.md` — boas práticas para TikTok Shop
