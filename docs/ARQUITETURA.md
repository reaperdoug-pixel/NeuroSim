# Arquitetura Técnica

O NeuroSim 3D é composto por um único arquivo, `index.html`, dividido em marcação (HTML/Tailwind), estilos e um bloco `<script>` com a lógica.

## Dependências (locais, em `vendor/`)

- Three.js r128, OrbitControls, EffectComposer, RenderPass, ShaderPass, CopyShader, LuminosityHighPassShader e UnrealBloomPass.
- Tailwind CSS e Google Fonts.

## Organização do JavaScript

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

## Páginas da interface

1. Cérebro 3D (visão livre) com mini-monitor de dopamina.
2. Gráfico e picos (curva dopaminérgica em canvas).
3. Detalhes e sinapse (conteúdo explicativo por substância).

## Fluxo de dados

O estado da simulação (substância primária e secundária, tempo, reprodução) alimenta o laço `animate`, que atualiza a cena 3D, calcula o nível de dopamina e a atividade do córtex pré-frontal e chama `updateHUDAndChart` para refletir os valores na interface.
