# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Público leigo e curioso, que chega por link ou redes e explora sozinho. Audiências adicionais confirmadas: jovens e famílias (foco em prevenção: apostas, drogas, vício), escola e professores (apoio didático em sala ou palestra) e profissionais de saúde (apoio em atendimento ou formação). O trabalho é entender, de forma visual, como o cérebro reage a substâncias e comportamentos de risco.

## Product Purpose

Plataforma educativa e interativa em 3D (Cortexplora, antigo NeuroSim 3D) que mostra, em tempo real, como o cérebro funciona em diferentes situações. O conteúdo é organizado em trilhas temáticas independentes. O objetivo é puramente didático; sucesso é o visitante sair compreendendo o mecanismo, sem julgamento.

## Positioning

Combina dois pontos que um vídeo ou infográfico não replica: (1) mecanismo visual, com cérebro 3D procedural, curva dopaminérgica ao vivo (absorção, pico, queda/crash) e comparativo entre duas substâncias no mesmo cérebro; (2) postura editorial neutra, informativa e sem julgamento, com trilhas independentes (condições do neurodesenvolvimento nunca no mesmo eixo que efeito de substâncias).

## Capabilities and Constraints

- Trilha Dopamapa (disponível): apostas eletrônicas, crack, cocaína, álcool, maconha (THC), sintéticas/MDMA. Versão 2.0 publicada em `index.html`: atlas com 10 regiões e vias, rótulos e foco de câmera, ranking e mapa de picos, indicador de dopamina em quatro estados, controle de velocidade, atalhos de teclado.
- Trilha Neurodiversidade (nome provisório): planejada.
- Arquivo único em HTML/CSS/JS puro, sem etapa de build; Three.js r128 e Tailwind 3.4.17 versionados em `vendor/`, funcionando sem CDN.
- Deve funcionar sem WebGL (gráfico, picos e detalhes continuam) e em telas pequenas.
- Conteúdo e terminologia em português do Brasil.
- Versão 1 arquivada em `index_v1.html`.
- Diretrizes editoriais e técnicas em `docs/TRILHAS.md`; arquitetura em `docs/ARQUITETURA.md`.

## Brand Commitments

Nome atual: Cortexplora (renomeado em outubro de 2026 por conflito de marca; endereço `cortexplora.degehub.io`, ver `docs/MIGRACAO_DE_NOME.md`). Evitar qualquer referência ao nome antigo em novas superfícies.

## Evidence on Hand

Produto publicado e documentação em `README.md`, `docs/` e `manual_de_uso.md`. Não há depoimentos, métricas de uso nem parcerias institucionais registradas; não inventar.

## Product Principles

1. Ciência sem julgamento: informar o mecanismo, nunca moralizar nem glamourizar.
2. Mecanismo antes de ornamento: o cérebro e a curva são o conteúdo, a interface serve a eles.
3. Trilhas independentes: temas distintos não se misturam no mesmo eixo comparativo.
4. Didático, não clínico: deixar claro que não é diagnóstico nem aconselhamento.
5. Leve e autônomo: arquivo único, offline, sem build.

## Accessibility & Inclusion

Funcionar sem WebGL, navegação por teclado, telas pequenas e contraste adequado. Linguagem acessível a leigos, em pt-BR. Aviso didático/médico visível.
