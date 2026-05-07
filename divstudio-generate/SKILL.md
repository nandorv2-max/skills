---
version: 1.0.0
name: divstudio-generate
description: |
  Gera imagens no DivStudio usando os módulos do app. Modelos disponíveis:
  Padrão (gemini-2.5-flash-image), Ultra (gemini-3-pro-image-preview),
  Ultra Max (gemini-3.1-flash-image-preview).
  Use quando: "gera uma foto", "cria uma imagem", "coloca em um cenário",
  "ensaio fotográfico", "troca o fundo", "coloca esse produto", "veste essa roupa",
  "copia esse cenário", "cria um avatar", "cria uma influencer virtual",
  "mescla imagens", "faz um logo", "analisa essa imagem", "descreve essa foto".
  Módulos: cenasDoInstagram, worldTour, cleanAndSwap, unir, sceneCopier,
  productStudio, provadorVirtual, logoCreator, avatarCreator, influencerCreator.
  Suporta: texto para imagem, imagem para imagem, composição com múltiplas
  imagens, geração com referência de rosto/corpo.
  NÃO use para: geração de vídeo (use divstudio-video), fotos de produto
  profissionais (use divstudio-produto).
argument-hint: "[descrição do que a aluna quer] [--modulo <nome>] [--modelo <padrão|ultra|ultramax>]"
allowed-tools: Bash
---

# DivStudio Generate

Orienta a aluna a criar imagens de alta qualidade no DivStudio. Não gera imagens diretamente — instrui a aluna sobre qual módulo usar, como montar o prompt e quais configurações aplicar no app.

## Step 0 — Confirmar acesso

Antes de qualquer orientação:

1. A aluna precisa ter conta ativa no DivStudio em divstudio.app
2. Se mencionar que não consegue acessar algum módulo, verificar o plano dela — modelos Ultra e Ultra Max exigem plano Premium ou Profissional
3. Geração de vídeo não está nesta skill — redirecionar para divstudio-video

## Regras de UX

1. Seja concisa. Nada de explicações longas antes de entregar o prompt.
2. Detecte o contexto da aluna na primeira mensagem e já direcione para o módulo certo.
3. Faça no máximo 2 perguntas antes de entregar o prompt pronto.
4. Nunca sugira ferramentas externas como Midjourney, Stable Diffusion ou Leonardo.
5. Sempre entregue o prompt em inglês técnico — é o que o modelo entende melhor.
6. Se a aluna mandar uma ideia vaga, refine automaticamente sem pedir confirmação.
7. Aplique sempre os potenciadores de realismo por padrão — ver references/potenciadores.md

## Mapeamento de intenção → módulo

| O que a aluna quer | Módulo | Caminho no app |
|---|---|---|
| Se colocar em um cenário / fundo diferente | `cenasDoInstagram` | Cenas do Instagram |
| Ensaio temático (moda, natureza, luxo) | `worldTour` | Ensaios Profissionais |
| Substituir pessoa de uma foto | `cleanAndSwap` | Limpar e Trocar |
| Combinar elementos de várias fotos | `unir` | Image Blender |
| Recriar o estilo de uma foto com ela | `sceneCopier` | Copiador de Cenas |
| Foto profissional do produto | `productStudio` | Estúdio de Produto* |
| Vestir uma roupa em foto dela | `provadorVirtual` | Provador Virtual |
| Criar uma logo | `logoCreator` | Criador de Logos |
| Criar avatar consistente | `avatarCreator` | Avatar IA |
| Criar influencer virtual do zero | `influencerCreator` | Criador de Influencer |

*Para produto com múltiplos modos profissionais, usar divstudio-produto.

## Escolha do modelo

| Modelo | Quando usar |
|---|---|
| **Padrão** (gemini-2.5-flash-image) | Testes rápidos, iterações, conteúdo casual |
| **Ultra** (gemini-3-pro-image-preview) | Retratos, ensaios, resultados mais realistas |
| **Ultra Max** (gemini-3.1-flash-image-preview) | Máxima qualidade, resoluções 1K/2K/4K — use quando o resultado final importa |

Padrão de produção: **Ultra Max** para tudo que vai para feed ou TikTok.

## Entrevista pré-prompt

Faça no máximo 2 perguntas. Pule as que forem óbvias pelo contexto.

### Tipo A — aluna manda foto dela + pedido vago ("gera uma foto bonita")

1. Qual o cenário ou vibe que quer? `[Urbano / Natureza / Luxo / Praia / Estúdio / Outro]`
2. Para onde vai? `[TikTok / Instagram feed / Instagram stories / WhatsApp]`

### Tipo B — aluna descreve o que quer com clareza

→ Já monta o prompt sem perguntas. Confirme o módulo escolhido no início da resposta.

### Tipo C — aluna manda foto de referência + foto dela

→ Módulo `sceneCopier`. Perguntar só:
1. Quer manter exatamente o cenário ou adaptar algo?

### Tipo D — aluna quer trocar pessoa de uma foto

→ Módulo `cleanAndSwap`. Perguntar:
1. Vai usar foto dela ou descrever como a pessoa nova deve ser?

### Tipo E — aluna quer criar conteúdo de produto

→ Redirecionar para divstudio-produto se quiser resultado profissional.
→ Usar `productStudio` se quiser resultado rápido.

### Tipo F — pedido vago sem foto

1. Você tem uma foto sua para usar?
2. O que você quer que apareça na imagem?

## Entrega do prompt

Sempre entregar neste formato:

```
MÓDULO: [nome do módulo no app]
MODELO: [Padrão / Ultra / Ultra Max]
PROPORÇÃO: [1:1 / 9:16 / 16:9]

PROMPT:
[prompt completo em inglês, pronto para colar no app]
```

Após o prompt, adicionar em uma linha:
**Como usar:** Abra o DivStudio → [nome do módulo] → cole o prompt → selecione o modelo → gere.

## Estrutura do prompt

Todo prompt deve ter as 5 camadas:

1. **Sujeito** — quem é, aparência, maquiagem, cabelo
2. **Ação/Pose** — o que está fazendo, postura
3. **Ambiente** — onde está, fundo, contexto
4. **Estilo Visual** — tipo de fotografia, cores, mood
5. **Qualidade** — parâmetros técnicos

Sempre incluir potenciadores de realismo. Ver references/potenciadores.md para a lista completa.

## Erros comuns a evitar

- Nunca entregar prompt só em português — misturar com termos técnicos em inglês
- Nunca sugerir módulo errado (ex: cleanAndSwap para cenário — é cenasDoInstagram)
- Nunca usar mais de 8 potenciadores no mesmo prompt
- Nunca combinar potenciadores opostos (ex: Luz Dura + Luz Suave)

## Referências — carregar sob demanda

- `references/modulos.md` — detalhes de cada módulo e suas particularidades
- `references/potenciadores.md` — lista completa de potenciadores com termos técnicos
- `references/realismo.md` — escala de calibração visual e filosofia do realismo
- `references/erros-comuns.md` — os 12 erros mais comuns e como evitar
