# Arquitetura Técnica

O Cortexplora é organizado em trilhas temáticas (consulte [TRILHAS.md](TRILHAS.md)). Atualmente existe uma trilha, o **Dopamapa**, disponível em duas versões, cada uma em um único arquivo HTML dividido em marcação (HTML/Tailwind), estilos e um bloco `<script>` com a lógica:

| Arquivo | Versão | Situação |
| --- | --- | --- |
| `index.html` | 2.0 | Publicada |
| `index_v1.html` | 1 | Arquivada (referência) |

O arquivo `index_v2.0.html` apenas redireciona para `index.html`, preservando links antigos da versão 2.0.

## Dependências (locais, em `vendor/`)

- Three.js r128, OrbitControls, EffectComposer, RenderPass, ShaderPass, CopyShader, LuminosityHighPassShader e UnrealBloomPass.
- Tailwind CSS 3.4.17 (Play CDN) e fontes Inter e JetBrains Mono (latin e latin-ext).

As duas versões carregam exclusivamente arquivos locais; nenhuma requisição é feita a CDNs externos.

## Versão 1 (`index_v1.html`)

| Grupo | Funções principais |
| --- | --- |
| Cena 3D | `initThreeScene`, `createProceduralParticleTexture`, `onWindowResize`, `focusCamera` |
| Modelagem procedural | `createDeformedHemisphereGeometry`, `buildProceduralCortex`, `buildPrefrontalCortexRegion`, `buildRewardCircuitStructures` |
| Vias e partículas | `buildDopaminergicBezierTracts`, `buildNeurotransmitterParticles`, `getPointOnPrimaryPath` |
| Laço de animação | `animate`, `updateFloatingLabels` |
| HUD e gráficos | `updateHUDAndChart`, `drawMiniSparkline`, `drawDopamineChart` |
| Interface e estado | `renderSubstanceTabs`, `selectPrimarySubstance`, `switchAppPage`, `toggleMiniHud` |
| Controle de tempo | `triggerSimulationEvent`, `togglePlayPause`, `onTimelineScrub`, `jumpToPeak`, `jumpToCrash` |
| Comparação | `toggleCompareMode`, `setSecondarySubstance`, `togglePeaksGuide`, `inspectSubstancePeak` |

## Versão 2.0 (`index.html`)

| Grupo | Funções e estruturas principais |
| --- | --- |
| Dados | `BRAIN_REGIONS` (atlas de 10 regiões e vias), `SUBSTANCES` (curvas por substância), `computeCurveExtremes`, `getDopamineStatus` |
| Cena 3D | `initThreeScene`, `showWebGLFallback`, `onWindowResize` |
| Modelagem procedural | `createDeformedHemisphereGeometry`, `buildProceduralCortex`, `buildPrefrontalCortexRegion`, `buildRewardCircuitStructures`, `buildGeodesicAnatomicalHubs`, `buildSelectedTargetBeacon` |
| Vias e partículas | `buildDopaminergicBezierTracts`, `buildNeurotransmitterParticles`, `getPointOnPrimaryPath`, `getParticleSpeedMult` |
| Laço de animação | `animate` (tempo e dados), `updateBrainScene` (somente 3D) |
| Rótulos anatômicos | `buildAnatomicalOverlayUI`, `updateFloatingLabelsAndLeaderLines`, `getPillSideLimits`, `focusBrainRegion` |
| HUD e gráficos | `updateHUDAndChart`, `updateCrashIndicator`, `drawMiniSparkline`, `drawDopamineChart`, `renderPeakLists` |
| Interface e estado | `renderSubstanceTabs`, `selectPrimarySubstance`, `switchAppPage`, `toggleMiniHud`, `toggleLeftAnatomyConsole`, `toggleAnatomicalLabels`, `applyCompactLayoutDefaults` |
| Controle de tempo | `triggerSimulationEvent`, `togglePlayPause`, `resetTimeline`, `setPlaybackSpeed`, `onTimelineScrub`, `initTimelineScrubbing`, `initChartClickScrubbing`, `jumpToPeak`, `jumpToCrash` |
| Comparação | `toggleCompareMode`, `setSecondarySubstance`, `inspectSubstancePeak` |
| Atalhos | `initKeyboardShortcuts` |

### Regras de dados

- **Picos e vales calculados:** `computeCurveExtremes` amostra cada `curveFn` uma única vez na inicialização (`CURVE_SAMPLES = 2000`) e grava o resultado em `sub.extremes`. O vale (crash) é procurado a partir de `CRASH_SEARCH_START = 0.3`, depois da fase de absorção. Rótulos, ranking, mapa rápido, gráficos e os botões "Ir ao Pico" e "Ir ao Crash" usam esses valores; nenhum pico deve ser escrito manualmente no HTML.
- **Estados de dopamina:** o nível basal é `DOPAMINE_BASELINE = 100` e o limiar de fissura é `CRASH_THRESHOLD = 92`. `getDopamineStatus` classifica o nível em `crash` (abaixo de 92%), `below` (de 92% a 99%), `baseline` (100%) ou `above` (acima de 100%).
- **Tempo normalizado:** todas as curvas usam o intervalo normalizado de 0 a 1, exibido como 60 segundos (`state.simDuration`). A escala é ilustrativa e não corresponde à duração real dos efeitos. A justificativa da escolha (comparação lado a lado no Modo Comparativo e ritmo de cerca de um minuto para acompanhar a subida, o pico e a queda) é exibida ao usuário na página Detalhes.
- **Escala de tempo real:** cada substância tem `realScale` e `realScaleNote`, exibidos em Detalhes com as fontes: NIDA (cocaína e crack, MDMA), CDC (maconha fumada, MMWR 2014) e Mackus et al., 2020 (eliminação do álcool). Não há escala de tempo estabelecida para a dopamina em apostas, e isso é declarado na interface. A maconha do modelo representa a via fumada.
- **Ponto em aberto:** os tempos de pico das curvas são parâmetros ilustrativos do modelo. Com a maconha fumada, as fontes indicam pico em cerca de 5 a 10 minutos, antes do início dos efeitos do MDMA (cerca de 45 minutos), mas no modelo o pico da maconha ocorre depois do pico do MDMA. Por isso a interface não afirma que a ordem de rapidez entre as curvas seja fiel à realidade.

### Comportamentos de interface

- **Atalhos de teclado:** Espaço (disparar evento), P (reproduzir/pausar), C (modo comparativo), L (rótulos) e 1 a 6 (substância). São ignorados quando Ctrl, Cmd ou Alt estão pressionados e quando o foco está em campos de texto.
- **Sem WebGL:** se a inicialização 3D falhar, `showWebGLFallback` exibe um aviso e o laço de animação continua atualizando a linha do tempo, o HUD e os gráficos 2D.
- **Telas estreitas (menos de 1024 px):** `applyCompactLayoutDefaults` inicia com o console anatômico, o painel lateral e os rótulos recolhidos, para que o modelo 3D permaneça visível.
- **Rótulos anatômicos:** as posições respeitam os limites reais do console anatômico e do painel lateral, calculados por `getPillSideLimits` a cada quadro.

## Páginas da interface

1. Cérebro 3D (visão livre) com painel de região e mini-monitor de dopamina.
2. Gráfico e picos (curva dopaminérgica em canvas e comparativo de picos).
3. Detalhes e sinapse (conteúdo explicativo por substância e, na versão 2.0, o atlas das regiões).

## Fluxo de dados

O estado da simulação (substância primária e secundária, tempo, reprodução e velocidade) alimenta o laço `animate`, que calcula o nível de dopamina e a atividade do córtex pré-frontal. Na versão 2.0, `animate` repassa esses valores a `updateBrainScene`, que atualiza a cena 3D quando o WebGL está disponível, e a `updateHUDAndChart`, que reflete os valores na interface.

## Organização em trilhas

Novas trilhas devem seguir as diretrizes técnicas de [TRILHAS.md](TRILHAS.md): dados em estruturas próprias, páginas próprias e reaproveitamento do motor 3D sem compartilhar escalas ou comparações com outras trilhas.
