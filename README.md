# Cortexplora

Plataforma educativa e interativa em 3D que mostra, de forma visual e em tempo real, como o cérebro funciona em diferentes situações. O conteúdo é organizado em trilhas temáticas independentes, voltadas a público leigo.

**Acesse online:** [cortexplora.degehub.io](https://cortexplora.degehub.io)

> O projeto se chamava **NeuroSim 3D**. O nome foi alterado em outubro de 2026 por conflito com marcas e softwares já existentes, e o endereço passou de `neurosim.degehub.io` para `cortexplora.degehub.io`. Consulte [docs/MIGRACAO_DE_NOME.md](docs/MIGRACAO_DE_NOME.md).

## Trilhas

| Trilha | Tema | Situação |
| --- | --- | --- |
| **Dopamapa** | Circuito de recompensa do cérebro durante o consumo de substâncias e em comportamentos de risco, como apostas eletrônicas | Disponível |
| **Neurodiversidade** (nome provisório) | Funcionamento do cérebro de pessoas no espectro autista, com TDAH e com outras condições do neurodesenvolvimento | Planejada |

As trilhas são independentes por princípio: condições do neurodesenvolvimento não são apresentadas no mesmo eixo que o efeito de substâncias. As diretrizes editoriais e técnicas estão em [docs/TRILHAS.md](docs/TRILHAS.md).

## Trilha Dopamapa

O Dopamapa apresenta um modelo cerebral tridimensional gerado proceduralmente e uma curva dopaminérgica dinâmica para cada substância, permitindo observar as fases de absorção, pico e queda (crash). O objetivo é puramente didático.

### Substâncias e comportamentos simulados

- Apostas eletrônicas (bets)
- Crack
- Cocaína
- Álcool
- Maconha (THC)
- Drogas sintéticas / MDMA

### Regiões cerebrais abordadas

- Versão 2.0, publicada (`index.html`): atlas com 10 regiões e vias, incluindo amígdala, córtices frontal, pré-frontal, parietal, temporal e occipital, VTA, Núcleo Accumbens e as vias mesolímbica e mesocortical.
- Versão 1, arquivada (`index_v1.html`): Área Tegmental Ventral (VTA), Núcleo Accumbens e Córtex Pré-Frontal.

### Funcionalidades

- Visualização 3D livre do cérebro (rotação e zoom).
- Gráfico da curva dopaminérgica em tempo real, com indicação de pico e alerta de fissura/crash.
- Página de detalhes com a ciência por trás de cada substância.
- Linha do tempo com play/pause e controle manual (scrub).
- Modo comparativo entre duas substâncias no mesmo cérebro.
- Partículas de neurotransmissores, vias dopaminérgicas e efeito de brilho (bloom).

A versão 2.0, atualmente publicada, acrescenta em relação à versão 1:

- Atlas anatômico com rótulos flutuantes, linhas-guia e foco de câmera por região.
- Ranking e mapa rápido de picos calculados diretamente a partir das curvas.
- Indicador de dopamina com quatro estados (acima do basal, no basal, abaixo do basal e fissura).
- Controle de velocidade da simulação e atalhos de teclado.
- Funcionamento sem WebGL (o gráfico, os picos e os detalhes continuam disponíveis) e layout adaptado a telas pequenas.

## Tecnologias

- HTML, CSS e JavaScript puro, em arquivo único, sem etapa de build.
- [Three.js](https://threejs.org/) r128 (renderização 3D, OrbitControls e pós-processamento).
- [Tailwind CSS](https://tailwindcss.com/) 3.4.17 (script do Play CDN).
- Fontes Inter e JetBrains Mono.

Todas as dependências estão versionadas na pasta `vendor/`, portanto o projeto funciona sem acesso a CDNs externos.

## Como executar

1. Clone o repositório.
2. Abra em um navegador moderno o arquivo `index.html` (versão 2.0). A versão 1 continua disponível em `index_v1.html`.

Não é necessária conexão com a internet, pois as bibliotecas e fontes estão em `vendor/`.

## Estrutura do repositório

| Arquivo | Descrição |
| --- | --- |
| `index.html` | Aplicação publicada (trilha Dopamapa, versão 2.0) |
| `index_v1.html` | Trilha Dopamapa, versão 1 (arquivada, mantida como referência) |
| `index_v2.0.html` | Redirecionamento para `index.html`, preserva links antigos da versão 2.0 |
| `manual_de_uso.md` | Manual de uso para o usuário final |
| `README.md` | Este documento |
| `CONTRIBUTING.md` | Orientações para contribuição |
| `LICENSE` | Licença MIT |
| `vendor/` | Bibliotecas e fontes locais (Three.js, Tailwind, Inter, JetBrains Mono) |
| `docs/ARQUITETURA.md` | Visão técnica do código |
| `docs/TRILHAS.md` | Conceito, diretrizes editoriais e técnicas das trilhas |
| `docs/MIGRACAO_DE_NOME.md` | Registro da mudança de nome e pendências de migração |

## Aviso

Este projeto possui finalidade exclusivamente educacional. Os modelos são simplificações ilustrativas e não substituem orientação médica, diagnóstico ou tratamento. Nenhuma trilha tem finalidade diagnóstica. Em caso de dependência química ou de comportamento compulsivo, procure um profissional de saúde.

## Licença

Distribuído sob a licença MIT. Consulte o arquivo [`LICENSE`](LICENSE) para mais detalhes.
