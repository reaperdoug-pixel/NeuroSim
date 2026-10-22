# Migração de Nome: NeuroSim 3D para Cada Cérebro

## Decisão

Em 22/10/2026, o projeto passou a se chamar **Cada Cérebro**. O nome **Dopamapa** passou a identificar a trilha sobre substâncias e comportamentos de risco. A estrutura de trilhas está descrita em [TRILHAS.md](TRILHAS.md).

## Motivo

O nome NeuroSim apresentava risco de conflito:

- **INPI:** há pedido da marca NEUROSIM (processo 934819661, depositado em 31/05/2024 por indústria farmacêutica, classe NCL 05, aguardando exame de mérito) e registro em vigor da marca @neurosimoestocantins (classe NCL 44).
- **Softwares homônimos no mesmo nicho:** o Neurosim da Universidade de St Andrews (software comercial de ensino de neurociência) e o NeuroSim da Universidade de Copenhague (simulador educativo de acesso aberto), além de outros projetos sem relação direta.

## Verificação de disponibilidade (22/10/2026)

Critérios: busca na web, busca de marcas no INPI (por radical, em todas as classes), consulta RDAP de domínios e busca de repositórios no GitHub.

| Nome | Web | INPI | `.com.br` | `.com` | GitHub |
| --- | --- | --- | --- | --- | --- |
| Cada Cérebro | Sem uso identificado | Sem resultados | Disponível | Disponível | Nenhum repositório |
| Dopamapa | Sem uso identificado | Sem resultados | Disponível | Disponível | Nenhum repositório |

Alternativas também disponíveis na data da verificação: Mentescópio, Cortexplora e Sinaptário.

Alternativas descartadas:

- **Cerebrário:** domínio `.com` em uso por agência criativa e repositório homônimo de visualização 3D de cérebro.
- **Cerebroscópio:** termo de dicionário para instrumento de diagnóstico, conotação inadequada.
- **Dopaminômetro:** existência do aplicativo "Dopaminometer", voltado à doença de Parkinson.
- **Cerebrália, PluralMente e Cerebrando:** domínios já registrados.

**Limitações:** esta verificação não constitui parecer jurídico. A busca no INPI abrange apenas o Brasil. Não foram consultados os registros dos Estados Unidos (USPTO) e da União Europeia (EUIPO), nem a disponibilidade de perfis em redes sociais.

## Pendências

- [ ] Registrar o domínio `cadacerebro.com.br` (opcionalmente, também `cadacerebro.com`).
- [ ] Depositar a marca no INPI, nas classes 41 (educação), 9 (software) e 42 (serviços de tecnologia).
- [ ] Criar o registro DNS de `cadacerebro.degehub.io` apontando para o GitHub Pages.
- [ ] Após a propagação do DNS, atualizar o arquivo `CNAME` para `cadacerebro.degehub.io` e configurar o domínio nas opções do GitHub Pages. Alterar o `CNAME` antes disso deixa o site fora do ar.
- [ ] Manter `neurosim.degehub.io` redirecionando para o novo endereço durante um período de transição (por exemplo, por regra no provedor de DNS ou por um repositório separado no GitHub Pages).
- [ ] Renomear o repositório `reaperdoug-pixel/NeuroSim` no GitHub. O GitHub redireciona automaticamente a URL antiga.
- [ ] Atualizar o link "Acesse online" do `README.md`.
- [ ] Opcional: renomear a pasta local do projeto.
