# Migração de Nome: NeuroSim 3D para Cortexplora

## Decisão

Em 22/10/2026, o projeto passou a se chamar **Cortexplora**. O nome **Dopamapa** identifica a trilha sobre substâncias e comportamentos de risco. A estrutura de trilhas está descrita em [TRILHAS.md](TRILHAS.md).

O nome **Cada Cérebro** chegou a ser adotado no mesmo dia, mas foi substituído por Cortexplora, considerado mais forte como marca. A expressão "cada cérebro é único" permanece disponível como slogan.

## Motivo

O nome NeuroSim apresentava risco de conflito:

- **INPI:** há pedido da marca NEUROSIM (processo 934819661, depositado em 31/05/2024 por indústria farmacêutica, classe NCL 05, aguardando exame de mérito) e registro em vigor da marca @neurosimoestocantins (classe NCL 44).
- **Softwares homônimos no mesmo nicho:** o Neurosim da Universidade de St Andrews (software comercial de ensino de neurociência) e o NeuroSim da Universidade de Copenhague (simulador educativo de acesso aberto), além de outros projetos sem relação direta.

## Verificação de disponibilidade (22/10/2026)

Critérios: busca na web, busca de marcas no INPI (por radical, em todas as classes), consulta RDAP de domínios e busca de repositórios no GitHub.

| Nome | Web | INPI | `.com.br` | `.com` | GitHub |
| --- | --- | --- | --- | --- | --- |
| Cortexplora | Sem uso identificado | Sem resultados para o nome | Disponível | Disponível | Nenhum repositório |
| Dopamapa | Sem uso identificado | Sem resultados | Disponível | Disponível | Nenhum repositório |
| Cada Cérebro (não adotado) | Sem uso identificado | Sem resultados | Disponível | Disponível | Nenhum repositório |

### Atenção: radical "cortex" no INPI

Embora o nome Cortexplora não tenha registros, a busca pelo radical "cortex" retornou marcas ativas nas classes de interesse do projeto:

- **Classe 41 (educação):** 33 processos, 13 vigentes ou em andamento, entre eles CÓRTEX e COLÉGIO CÓRTEX (empresa educacional) e Cortex Academy.
- **Classe 42 (serviços de tecnologia):** 58 processos, 30 vigentes ou em andamento, entre eles diversas marcas CORTEX da Cortex Intelligence Tecnologia S.A.

Como o nome começa pelo mesmo elemento, um depósito de marca pode sofrer oposição. Recomenda-se consultar especialista em propriedade industrial antes do depósito.

### Alternativas

Também disponíveis na data da verificação: Mentescópio e Sinaptário.

Descartadas:

- **Cerebrário:** domínio `.com` em uso por agência criativa e repositório homônimo de visualização 3D de cérebro.
- **Cerebroscópio:** termo de dicionário para instrumento de diagnóstico, conotação inadequada.
- **Dopaminômetro:** existência do aplicativo "Dopaminometer", voltado à doença de Parkinson.
- **Cerebrália, PluralMente e Cerebrando:** domínios já registrados.

**Limitações:** esta verificação não constitui parecer jurídico. A busca no INPI abrange apenas o Brasil. Não foram consultados os registros dos Estados Unidos (USPTO) e da União Europeia (EUIPO), nem a disponibilidade de perfis em redes sociais.

## Endereço online

- **DNS:** registro CNAME `cortexplora` apontando para `reaperdoug-pixel.github.io`, na zona `degehub.io` (Hostinger). O registro provisório `cadacerebro` foi removido.
- **GitHub Pages:** domínio personalizado `cortexplora.degehub.io`, definido no arquivo `CNAME`.
- **Endereço antigo:** o registro DNS `neurosim` foi removido em 22/10/2026. Como ele apontava para o GitHub Pages sem um site associado, havia risco de sequestro do subdomínio (*subdomain takeover*). O endereço `neurosim.degehub.io` passou a ser atendido pelo registro curinga (`*`) da zona e não exibe mais o projeto.

## Pendências

- [x] Criar o registro DNS de `cortexplora.degehub.io` apontando para o GitHub Pages.
- [x] Atualizar o arquivo `CNAME` e o domínio do GitHub Pages para `cortexplora.degehub.io`.
- [x] Atualizar o link "Acesse online" do `README.md`.
- [x] Remover o registro DNS de `neurosim.degehub.io`, que apontava para o GitHub Pages sem site associado.
- [ ] Quando o projeto estiver concluído, registrar o domínio `cortexplora.com.br` (opcionalmente, também `cortexplora.com`).
- [ ] Quando o projeto estiver concluído, consultar especialista e depositar a marca no INPI, nas classes 41 (educação), 9 (software) e 42 (serviços de tecnologia).
- [ ] Opcional: redirecionar `neurosim.degehub.io` para o novo endereço por regra de redirecionamento na Hostinger. Não recrie um CNAME para o GitHub Pages sem um site associado a ele.
- [ ] Opcional: renomear o repositório `reaperdoug-pixel/NeuroSim` no GitHub. O GitHub redireciona automaticamente a URL antiga.
- [ ] Opcional: renomear a pasta local do projeto.
