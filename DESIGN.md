---
name: Cortexplora
description: Atlas 3D do cérebro sobre vidro escuro, com curvas dopaminérgicas que brilham em tempo real.
colors:
  deep-space: "#0A0E17"
  deep-space-glow: "#131c31"
  glass-panel: "rgba(11, 17, 30, 0.80)"
  ice-white: "#F8FAFC"
  slate-text: "#94A3B8"
  slate-line: "rgba(148, 163, 184, 0.15)"
  signal-cyan: "#38BDF8"
  signal-cyan-text: "#67E8F9"
  crash-rose: "#F43F5E"
  crash-rose-soft: "#FB7185"
  caution-amber: "#FCD34D"
typography:
  body:
    fontFamily: "Inter, sans-serif"
    fontWeight: 400
  label-mono:
    fontFamily: "JetBrains Mono, monospace"
    fontWeight: 500
rounded:
  pill: "999px"
  full: "50%"
components:
  hud-panel:
    backgroundColor: "{colors.glass-panel}"
    textColor: "{colors.ice-white}"
  anat-pill:
    backgroundColor: "rgba(10, 15, 28, 0.82)"
    textColor: "{colors.ice-white}"
    rounded: "{rounded.pill}"
  anat-pill-active:
    backgroundColor: "rgba(14, 116, 144, 0.28)"
    textColor: "{colors.signal-cyan-text}"
    rounded: "{rounded.pill}"
  slider-thumb:
    backgroundColor: "{colors.signal-cyan}"
    rounded: "{rounded.full}"
    size: "16px"
---

# Design System: Cortexplora

## Overview

**Creative North Star: "O Observatório do Cérebro"**

O cérebro é um corpo celeste em um céu escuro, e a interface é o equipamento de observação ao redor dele. O fundo é um azul-noite quase preto com um halo suave no centro e um grid holográfico tênue; os controles flutuam como vidro fosco sobre esse céu. O conteúdo (modelo 3D, curva, picos) brilha; a moldura recua.

A densidade é a de um instrumento: muita informação em painéis compactos, números em fonte monoespaçada, hierarquia por brilho e não por cor de fundo. O tom é científico e calmo, sem dramatizar. O vermelho-rosado aparece somente para o estado de fissura/crash, onde o alerta é parte do conteúdo didático.

**Key Characteristics:**
- Escuro por natureza: a cena 3D exige fundo noturno, não é preferência de tema.
- Vidro fosco com blur sobre a cena, nunca painéis opacos.
- Brilho ciano marca foco, seleção e interação; rosa marca fissura/crash.
- Cápsulas arredondadas para rótulos, abas e controles.

## Colors

Paleta noturna fria com um único acento ciano e um alerta rosa reservado.

### Primary
- **Ciano de Sinal** (#38BDF8): foco, seleção, thumb do slider, bordas ativas e brilho de destaque. Texto ciano sobre escuro usa o tom mais claro (#67E8F9).

### Secondary
- **Rosa de Crash** (#F43F5E, claro #FB7185): exclusivo do estado de fissura/crash, com borda e brilho pulsantes.
- **Âmbar de Atenção** (#FCD34D): avisos e valores de cautela, uso pontual.

### Neutral
- **Espaço Profundo** (#0A0E17): fundo de página; o centro da cena clareia para #131c31.
- **Vidro HUD** (rgba(11, 17, 30, 0.80)): fundo dos painéis, sempre com blur.
- **Branco Gelo** (#F8FAFC): texto principal.
- **Ardósia** (#94A3B8): texto secundário e linhas finas (a 15% de opacidade).

No código, essas cores são variáveis CSS no `:root` do `index.html` (`--bg-deep`, `--bg-deep-glow`, `--ice-white`, `--signal-cyan`, `--crash-rose-soft`, e os canais `--signal-cyan-rgb`, `--crash-rose-rgb`, `--slate-line-rgb`, `--glass-rgb` para transparências). O JavaScript (canvas dos gráficos e a névoa do Three.js) lê esses mesmos tokens pelo objeto `UI_COLORS`, sem repetir valores.

Cada substância e região tem sua própria cor de dado (âmbar nas Apostas, vermelho no crack, rosa na cocaína, azul no álcool, turquesa na maconha, violeta no MDMA, definidas em `colorHex` no código). Elas colorem curvas e pontos, nunca a interface.

### Named Rules
**The One Signal Rule.** Ciano é o único acento da interface. Cores de substância vivem só dentro dos dados.
**The Crash Is Rose Rule.** Rosa pulsante aparece apenas quando a dopamina está em fissura/crash.

## Typography

**Body Font:** Inter (com sans-serif)
**Label/Mono Font:** JetBrains Mono (com monospace)

**Character:** Inter dá leitura limpa para texto didático; JetBrains Mono dá cara de instrumento aos números, rótulos técnicos e valores da curva.

### Hierarchy
- **Título da substância** (700, 18px no celular e 20px a partir de `sm`): o nome da substância ou comportamento em Detalhes.
- **Marca e títulos de seção** (700, 14px, mono; a marca com 0,16em de espaçamento): CORTEXPLORA e os títulos de painel.
- **Body** (400, 14px com entrelinha 1,65 em Detalhes, texto em Branco Gelo ou Ardósia): explicações e descrições para leigos.
- **Label** (mono, 12px de piso, caixa-alta quando técnico): valores, unidades, rótulos de região e de eixo. Nada fica abaixo de 12px.

### Named Rules
**The Numbers Are Mono Rule.** Todo valor numérico da simulação usa a fonte mono.

## Layout

Cena em tela cheia (canvas 3D) com camadas sobrepostas: grid holográfico, rótulos e linhas-guia em SVG, e painéis HUD flutuantes. A página não rola; os painéis rolam internamente com barra fina (5px). Em telas pequenas o layout se reorganiza e as abas rolam na horizontal sem barra visível. O espaçamento segue a escala do Tailwind.

## Elevation & Depth

Híbrido de vidro e luz. A profundidade vem de transparência com blur (14px nos painéis, 8px nas cápsulas), uma sombra grande e escura sob o painel e um filete de luz no topo. Estados ativos emitem brilho (glow) em vez de subir.

### Shadow Vocabulary
- **Painel HUD** (`box-shadow: 0 12px 32px -4px rgba(0,0,0,0.65), inset 0 1px 0 0 rgba(255,255,255,0.07)`): painéis flutuantes.
- **Glow ativo** (`box-shadow: 0 0 18px rgba(56,189,248,0.35)`): cápsula selecionada.
- **Glow do thumb** (`box-shadow: 0 0 12px rgba(56,189,248,0.9)`): controle deslizante.
- **Pulso de crash** (animação `crashPulse`, 1,4s, rosa): estado de fissura.

### Named Rules
**The Glow Is State Rule.** Brilho só aparece em foco, seleção ou alerta, nunca como decoração em repouso.

## Shapes

Cápsulas e círculos. Rótulos, abas e trilhos usam cantos totalmente arredondados (999px); thumb e pontos são círculos. Bordas finas de 1px em Ardósia a 15–22% de opacidade delimitam o vidro.

## Components

### Painel HUD
- **Fundo:** vidro escuro com blur de 14px, borda de 1px, sombra profunda e filete de luz no topo.

### Cápsula anatômica
- **Repouso:** fundo escuro translúcido, blur 8px, borda 1px (22%).
- **Hover:** escala 1.05, borda ciano a 65%, fundo mais opaco; transição 0.2s `cubic-bezier(0.16, 1, 0.3, 1)`.
- **Ativa:** borda ciano sólida, fundo teal a 28%, glow ciano.

### Slider
- **Trilho:** 6px, pílula, fundo azul-ardósia, borda fina.
- **Thumb:** círculo de 16px ciano com anel branco de 2px e glow; hover escala 1.18.

### Botão de ação principal
- **Estilo:** ciano sólido (`bg-cyan-500`) com texto escuro `slate-950`, borda ciano clara e hover em ciano mais claro. É o único botão preenchido da interface ("SIMULAR EVENTO").

### Cartão de apresentação e fecho
- **Estilo:** folha de vidro posicionada logo acima do rodapé de controles, com botão de fechar de 44px, com passo, título, texto curto e dois botões (secundário neutro, primário ciano). Aparece na primeira visita e ao fim de uma simulação disparada pelo usuário, com resumo da curva e a linha de apoio (CVV 188).

### Alerta de crash
- Borda e brilho rosa pulsando (inset e externo), apenas no estado de fissura.

## Do's and Don'ts

### Do:
- **Do** usar vidro translúcido com blur sobre a cena 3D.
- **Do** reservar ciano para foco e seleção e rosa para crash.
- **Do** usar JetBrains Mono em todo valor numérico.
- **Do** manter transições curtas (0.15–0.2s) e brilho como resposta de estado.

### Don't:
- **Don't** usar painéis opacos que escondam o cérebro.
- **Don't** colorir a interface com as cores das substâncias.
- **Don't** usar brilho como decoração em repouso.
- **Don't** usar fundos claros: a cena depende do céu noturno.
