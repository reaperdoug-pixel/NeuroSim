# Guia de Contribuição

Obrigado pelo interesse em contribuir com o Cortexplora (anteriormente NeuroSim 3D).

## Fluxo sugerido

1. Crie um fork ou uma branch a partir da `main`.
2. Faça alterações pequenas e focadas.
3. Teste manualmente no navegador: as três páginas, o modo comparativo, a linha do tempo e, na versão 2.0, os rótulos anatômicos, os atalhos de teclado e a exibição em tela pequena.
4. Abra um Pull Request descrevendo o que mudou e por quê.

## Diretrizes

- Cada versão da aplicação é um arquivo HTML único. Evite introduzir etapa de build sem discussão prévia.
- Mantenha o conteúdo científico fiel a fontes confiáveis e cite-as no PR.
- Preserve o tom educativo e responsável do material.
- Respeite a separação entre trilhas e as diretrizes editoriais descritas em [docs/TRILHAS.md](docs/TRILHAS.md), especialmente a linguagem não patologizante e a revisão especializada de conteúdo sobre neurodesenvolvimento.
- Não escreva valores de pico ou de vale manualmente no HTML: na versão 2.0 eles são calculados a partir das curvas em `SUBSTANCES`.
- Documentação em português (pt-BR), em tom formal.

## Reportar problemas

Abra uma issue informando navegador, sistema operacional, passos para reproduzir e, se possível, uma captura de tela.
