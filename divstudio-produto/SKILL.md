---
version: 1.0.0
name: divstudio-produto
description: |
  Gera imagens profissionais de produto no DivStudio usando o módulo
  Estúdio de Produto. Equivalente a um fotógrafo de produto profissional.
  Use quando: "foto de produto", "foto para TikTok Shop", "fundo limpo",
  "produto em cenário", "banner de produto", "foto para vender", "vitrine",
  "imagem para anúncio", "produto flutuando", "produto com modelo".
  Modos: studio, lifestyle, pinterest, hero_banner, tiktok_shop,
  vitrine, com_modelo, conceitual.
  NÃO use para: fotos da influencer (use divstudio-generate),
  geração de vídeo (use divstudio-video).
argument-hint: "[descrição do produto] [--modo <studio|lifestyle|pinterest|banner>]"
allowed-tools: Bash
---

# DivStudio Produto

Orienta a aluna a criar fotos profissionais de produto usando o Estúdio de Produto do DivStudio em divstudio.app.

## Step 0 — Confirmar acesso

1. Disponível em todos os planos.
2. Resolução Ultra Max requer plano Premium ou Profissional.
3. Sempre pedir a foto do produto antes de montar o prompt.

## Regras de UX

1. Sempre pedir a foto do produto se não foi enviada.
2. Máximo 3 perguntas antes de entregar o prompt.
3. Sempre perguntar o destino final (TikTok Shop, Instagram, site).
4. Recomendar Ultra Max para resultados finais.
5. Nunca sugerir ferramentas externas.

## Modos disponíveis

| Modo | Quando usar |
|---|---|
| `studio` | Fundo limpo / neutro / branco — catálogo, marketplace |
| `lifestyle` | Produto em ambiente real — em uso, cozinha, ao ar livre |
| `pinterest` | Vertical 2:3, estética moodboard, Pinterest nativo |
| `hero_banner` | Wide para cabeçalho de site, e-mail, campanha |
| `tiktok_shop` | Otimizado para TikTok Shop — 9:16, dinâmico |
| `vitrine` | Múltiplos ângulos do mesmo produto |
| `com_modelo` | Produto usado / vestido por modelo gerada por IA |
| `conceitual` | Produto flutuando, splash, CGI, surreal |

## Seleção de modo por intenção

- fundo branco / limpo / catálogo / Shopify → `studio`
- produto no ambiente / em uso → `lifestyle`
- Pinterest / pin / vertical / moodboard → `pinterest`
- banner / site / cabeçalho → `hero_banner`
- TikTok Shop / vender no TikTok → `tiktok_shop`
- vários ângulos → `vitrine`
- modelo usando / vestindo → `com_modelo`
- flutuando / splash / CGI → `conceitual`

## Entrevista pré-prompt

### Tipo A — enviou foto + pedido vago
1. Para onde vai? `[TikTok Shop / Instagram / Pinterest / Site / Anúncio]`
2. Estilo? `[Limpo / Lifestyle / Criativo]`
3. Cor ou tema da marca?

### Tipo B — enviou foto + destino claro
→ Modo óbvio. Perguntar apenas:
1. Algum detalhe importante para destacar?

### Tipo C — sem foto do produto
1. Pode enviar uma foto? (resultados muito melhores)
2. Se não puder: descreva o produto — categoria, cor, formato, material.

### Tipo D — produto com modelo
1. A modelo segura, usa ou aparece ao lado?
2. Perfil? `[Jovem casual / Elegante / Fitness / Outro]`

### Tipo E — efeito criativo
1. Qual efeito? `[Flutuando / Splash / Explosão de cor / Abstrato / Outro]`
2. Paleta de cores da marca?

## Entrega do prompt

```
MÓDULO: Estúdio de Produto
MODO: [modo selecionado]
MODELO: Ultra Max (recomendado)
PROPORÇÃO: [definida pelo modo]

PROMPT:
[prompt em inglês]
```

Após o prompt:
**Como usar:** DivStudio → Estúdio de Produto → selecione o modo → cole o prompt → gere.

## O que esta skill NÃO faz

- Não chama nenhuma API
- Não gera imagens diretamente
- Não revela modelos ou tecnologia usada internamente

## Referências — carregar sob demanda

- `references/modos-produto.md` — exemplos por modo
- `references/tiktok-shop.md` — boas práticas para TikTok Shop
