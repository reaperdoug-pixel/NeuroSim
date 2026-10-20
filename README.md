# NeuroSim 3D

Simulador educativo e interativo em 3D que demonstra, em tempo real, o que ocorre no circuito de recompensa do cérebro durante o consumo de diferentes substâncias e em comportamentos de risco, como apostas eletrônicas.

## Visão geral

O NeuroSim 3D apresenta um modelo cerebral tridimensional gerado proceduralmente e uma curva dopaminérgica dinâmica para cada substância, permitindo observar as fases de absorção, pico e queda (crash). O objetivo é puramente didático, voltado a público leigo.

### Substâncias e comportamentos simulados

- Apostas eletrônicas (bets)
- Crack
- Cocaína
- Álcool
- Maconha (THC)
- Drogas sintéticas / MDMA

### Regiões cerebrais abordadas

- Área Tegmental Ventral (VTA)
- Núcleo Accumbens
- Córtex Pré-Frontal

## Funcionalidades

- Visualização 3D livre do cérebro (rotação e zoom).
- Gráfico da curva dopaminérgica em tempo real, com indicação de pico e alerta de fissura/crash.
- Página de detalhes com a ciência por trás de cada substância.
- Linha do tempo com play/pause e controle manual (scrub).
- Modo comparativo entre duas substâncias no mesmo cérebro.
- Partículas de neurotransmissores, vias dopaminérgicas e efeito de brilho (bloom).

## Tecnologias

- HTML, CSS e JavaScript puro, em arquivo único, sem etapa de build.
- [Three.js](https://threejs.org/) r128 (renderização 3D, OrbitControls e pós-processamento).
- [Tailwind CSS](https://tailwindcss.com/) via CDN.
- Fontes Inter e JetBrains Mono (Google Fonts).

## Como executar

1. Clone o repositório.
2. Abra o arquivo `index.html` em um navegador moderno.

É necessária conexão com a internet para o carregamento das bibliotecas via CDN.

## Estrutura do repositório

| Arquivo | Descrição |
| --- | --- |
| `index.html` | Aplicação completa |
| `manual_de_uso.md` | Manual de uso para o usuário final |
| `README.md` | Este documento |
| `CONTRIBUTING.md` | Orientações para contribuição |
| `LICENSE` | Licença MIT |
| `docs/ARQUITETURA.md` | Visão técnica do código |

## Aviso

Este projeto possui finalidade exclusivamente educacional. Os modelos são simplificações ilustrativas e não substituem orientação médica, diagnóstico ou tratamento. Em caso de dependência química ou de comportamento compulsivo, procure um profissional de saúde.

## Licença

Distribuído sob a licença MIT. Consulte o arquivo [`LICENSE`](LICENSE) para mais detalhes.
