---
name: dama-dmbok-arquitetura-dados
description: >
  Aplica os princípios de Arquitetura de Dados do DAMA-DMBOK2 (capítulo 4) para projetar, documentar
  e revisar a arquitetura de dados de qualquer organização — do sistema transacional de origem até o
  modelo semântico de BI, em qualquer setor de negócio. Use esta skill sempre que o usuário pedir para
  desenhar/revisar uma arquitetura de dados, definir o fluxo Fonte → Stage → DW → DM → Modelo Semântico,
  avaliar um modelo de dados corporativo (Enterprise Data Model), decidir sobre desacoplamento entre
  transacional e analítico, mapear fluxos de dados entre um sistema de origem e uma camada analítica,
  ou questionar riscos de escalabilidade, governança e manutenibilidade em uma proposta de arquitetura.
  Aplique também quando pedirem uma "arquitetura de referência", "blueprint de dados" ou "roadmap de
  integração de dados".
---

# DAMA-DMBOK2 — Arquitetura de Dados (Capítulo 4)

Esta skill traduz e aplica o capítulo de Arquitetura de Dados do DAMA-DMBOK2 de forma genérica, para
qualquer pessoa que precise projetar ou avaliar arquitetura de dados, em qualquer setor de negócio e com
qualquer stack tecnológico. Os princípios abaixo não dependem de um domínio de negócio nem de um conjunto
de ferramentas específico — use-os para embasar tecnicamente decisões de arquitetura, não para produzir
texto genérico de "boas práticas".

## Definição (DMBOK2)

Arquitetura de Dados é a identificação das necessidades de dados da organização (independente de estrutura)
e o desenho e manutenção dos blueprints mestres que atendem a essas necessidades — usando esses blueprints
para guiar a integração de dados, controlar os ativos de dados e alinhar os investimentos em dados com a
estratégia de negócio. O objetivo é ser a ponte entre estratégia de negócio e execução tecnológica.

O artefato mais detalhado de Arquitetura de Dados é o **modelo de dados corporativo (Enterprise Data Model —
EDM)**, contendo nomes de dados, definições completas de dados e metadados, entidades e relacionamentos
conceituais/lógicos, e regras de negócio. Modelos físicos pertencem à modelagem de dados (ver skill
`dama-dmbok-modelagem-dados`), não à Arquitetura de Dados propriamente.

## Objetivos e drivers de negócio

1. Identificar requisitos de armazenamento e processamento de dados.
2. Desenhar estruturas e planos que atendam às necessidades de dados atuais e de longo prazo da organização.
3. Preparar a organização para evoluir produtos, serviços e dados aproveitando oportunidades tecnológicas.
4. Traduzir necessidades de negócio em requisitos de dados e sistemas, para que os processos tenham
   consistentemente os dados de que precisam.
5. Facilitar o alinhamento entre negócio e TI.

Esses drivers devem orientar a métrica de valor de qualquer trabalho de arquitetura — se uma proposta não
reduz custo, risco ou tempo de entrega de dados confiáveis, questione sua justificativa.

## Conceitos essenciais

### Enterprise Data Model (EDM)
Modelo de dados holístico, de nível corporativo, independente de implementação, que fornece uma visão
comum e consistente dos dados através da organização. Inclui entidades de negócio centrais, relacionamentos,
regras de negócio críticas e atributos-chave. Todo modelo de dados de projeto deve derivar do EDM — não o
contrário. Construção incremental e iterativa é a norma: comece bottom-up a partir dos modelos de dados já
existentes e complete o EDM delegando a modelagem de subject areas a projetos específicos.

Níveis do EDM (do mais abstrato ao mais físico): modelo conceitual da organização → modelos de subject area
→ modelos lógicos por subject area → modelos lógicos/físicos específicos de aplicação/projeto. Rastreabilidade
vertical (um atributo físico deve ser rastreável até o conceito de negócio que representa) e horizontal (a mesma
entidade pode aparecer em múltiplas subject areas, relacionada como link externo) são exigências de governança
e auditabilidade, não luxo acadêmico.

### Data Flow Design
Documentação de linhagem que mostra como os dados se movem entre processos e sistemas: onde se originam,
onde são armazenados/usados e como são transformados. Pode ser representada em matriz (processos de negócio
x entidades principais, indicando Create/Read) ou em diagrama de fluxo. Isso é rastreabilidade de ponta a ponta
— essencial para responder "de onde veio esse número no relatório".

### Domínios de Arquitetura Empresarial
Arquitetura de Dados é um dos domínios da Arquitetura Empresarial (junto com negócio, aplicação e tecnologia).
Decisões de arquitetura de dados isoladas da arquitetura de aplicações e infraestrutura tendem a gerar
integrações ad-hoc não governadas — o oposto do que se busca em um DW corporativo.

## Atividades principais

1. **Estabelecer a prática de Arquitetura de Dados**: avaliar especificações existentes, desenvolver roadmap,
   gerenciar requisitos corporativos dentro de projetos.
2. **Integrar com a Arquitetura Empresarial**: garantir que o EDM e os fluxos de dados estejam alinhados com
   arquitetura de aplicações, infraestrutura e estratégia de negócio.

Ferramentas típicas: ferramentas de modelagem de dados, software de gestão de ativos, aplicações de desenho
gráfico. Métricas típicas: taxas de conformidade com padrões de arquitetura, tendências de implementação,
métricas de valor de negócio.

## Princípios práticos de aplicação

Estes princípios se aplicam a qualquer organização, independente do setor. A arquitetura de referência mais
comum segue o pipeline:

**Fonte (sistema transacional) → Stage → DW → DM → Modelo Semântico → Relatórios**

- **EDM mínimo viável antes do DW físico.** Antes de desenhar tabelas de Stage/DW, formalize um modelo
  conceitual das subject areas do negócio (as entidades centrais variam por setor: cliente, produto,
  contrato, pedido, estoque, unidade organizacional etc.). Sem isso, cada integração vira um mapeamento
  ad-hoc do schema de origem direto para a camada de BI, e a regra de negócio se espalha por dashboards —
  exatamente o antipadrão que o DMBOK descreve como "spaghetti de interfaces".
- **Rastreabilidade Fonte → DW → Modelo Semântico é auditável, não documentação opcional.** Em qualquer
  organização com exigências de auditoria, compliance ou prestação de contas, a pergunta "de onde veio esse
  número" é recorrente. Mantenha um Data Flow Design (matriz ou diagrama) até o nível de entidade principal,
  não apenas a nível de sistema.
- **Desacoplamento real entre transacional e analítico.** O sistema de origem é o sistema de registro; o
  banco analítico/DW não deve ser um espelho 1:1 do schema transacional — isso apenas transporta o problema
  de modelagem do sistema de origem para o DW. Trate a camada de Stage como zona de aterrissagem sem lógica
  de negócio, e o DW como onde a arquitetura dimensional (Kimball) e as regras de negócio (SCD2, chaves
  substitutas) são aplicadas.
- **Chave única entre entidades organizacionais correlatas** (ex: unidade de negócio / unidade operacional /
  filial, ou qualquer hierarquia equivalente do domínio). Esta costuma ser a maior lacuna de padronização
  cadastral em organizações com baixa maturidade de dados, em qualquer setor. Resolva-a na Arquitetura de
  Dados (como parte do EDM), não na camada de relatório — se cada relatório reconciliar isso de forma
  independente, a governança já falhou.
- **Antes de propor uma tecnologia específica**, valide se o problema é de arquitetura (falta de blueprint,
  subject areas não definidas) ou de ferramenta. DMBOK é enfático: arquitetura não é sobre a ferramenta, é
  sobre o desenho que a ferramenta implementa. Em ambientes com infraestrutura limitada ou conectividade
  instável, penalize arquiteturas que dependem de sincronização em tempo real sem necessidade real de
  negócio.

## Checklist de diagnóstico

Ao revisar ou propor uma arquitetura de dados, verifique:

- Existe um EDM (ainda que mínimo) documentado, ou a integração foi feita ponto a ponto sem modelo de
  referência?
- As subject areas do negócio estão definidas e nomeadas de forma consistente entre o sistema de origem,
  o DW e a camada de BI?
- Existe rastreabilidade documentada (data flow) do dado, da origem ao relatório final?
- A camada transacional está desacoplada da camada analítica, ou o DW é apenas uma cópia do schema de
  origem?
- Regras de negócio estão centralizadas na arquitetura de dados/DW, ou espalhadas em múltiplos dashboards?
- A proposta de arquitetura considera a infraestrutura e a maturidade de dados reais da organização, ou
  assume um cenário corporativo maduro que não existe na prática?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 4,
Data Architecture.
