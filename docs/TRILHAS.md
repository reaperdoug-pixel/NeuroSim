# Trilhas de Conteúdo

## Conceito

O Cortexplora parte da premissa de que cada cérebro funciona de uma forma. A plataforma organiza o conteúdo em **trilhas** temáticas independentes, cada uma com objetivo, dados e linguagem próprios, compartilhando apenas o motor de visualização 3D e o padrão de interface.

## Trilhas

### Dopamapa (disponível)

- **Tema:** circuito de recompensa do cérebro durante o consumo de substâncias e em comportamentos de risco.
- **Conteúdo:** apostas eletrônicas (bets), crack, cocaína, álcool, maconha (THC) e drogas sintéticas (MDMA).
- **Arquivos:** `index.html` (versão 1, publicada) e `index_v2.0.html` (versão 2.0, em desenvolvimento).
- **Dados:** `SUBSTANCES` (curvas de dopamina e de atividade do córtex pré-frontal) e, na versão 2.0, `BRAIN_REGIONS` (atlas anatômico).
- **Limitações declaradas:** as curvas são modelos ilustrativos em tempo normalizado (60 segundos) e não representam medições reais nem a duração real dos efeitos.

### Neurodiversidade (planejada; nome provisório)

- **Tema previsto:** funcionamento do cérebro de pessoas no espectro autista (TEA), com TDAH e com outras condições do neurodesenvolvimento.
- **Abordagem:** apresentar diferenças de funcionamento, como processamento sensorial, atenção, funções executivas e conectividade entre regiões, sem tratá-las como defeitos a corrigir.
- **Situação:** em planejamento. Nenhum conteúdo deve ser publicado antes da revisão especializada descrita abaixo.

## Diretrizes editoriais

1. **Separação de eixos:** as trilhas não compartilham escalas, gráficos, rankings ou comparações. Uma condição do neurodesenvolvimento nunca é comparada a uma substância nem apresentada como "efeito".
2. **Linguagem não patologizante:** prefira "pessoa autista" ou "pessoa no espectro autista" e "condição" em vez de "doença". Evite expressões como "sofre de" e "portador de". Quando houver divergência de preferência na comunidade, registre a escolha adotada neste documento.
3. **Sem finalidade diagnóstica:** nenhuma tela deve sugerir autoavaliação, triagem ou diagnóstico. Sempre que pertinente, oriente a busca por profissionais e serviços de saúde.
4. **Revisão especializada:** o conteúdo sobre neurodesenvolvimento deve ser revisado por profissional da área (por exemplo, neurologia, psiquiatria ou neuropsicologia) e, preferencialmente, por pessoas neurodivergentes antes da publicação.
5. **Fontes:** toda afirmação científica deve ter fonte confiável registrada no Pull Request ou na documentação.
6. **Valores ilustrativos identificados:** números, curvas e escalas que forem simplificações devem ser identificados como tal na própria interface.
7. **Apoio:** cada trilha deve exibir aviso educacional e indicar onde buscar ajuda. Na trilha Dopamapa, por exemplo, os Centros de Atenção Psicossocial Álcool e Drogas (CAPS AD).

## Diretrizes técnicas para uma nova trilha

- **Dados próprios:** use estruturas separadas (por exemplo, `NEURO_PROFILES`), sem reutilizar `SUBSTANCES` nem suas escalas.
- **Páginas próprias:** a trilha deve ter páginas e navegação próprias, selecionáveis a partir da navegação principal.
- **Reaproveitamento:** reutilize o motor 3D (cena, modelagem procedural, `BRAIN_REGIONS` e rótulos anatômicos) e o padrão de painéis da interface.
- **Identidade:** cada trilha exibe seu selo no cabeçalho, ao lado da marca, como o selo "Dopamapa".
- **Documentação:** ao criar ou alterar uma trilha, atualize este documento, o `README.md`, o `manual_de_uso.md` e o `docs/ARQUITETURA.md`.
