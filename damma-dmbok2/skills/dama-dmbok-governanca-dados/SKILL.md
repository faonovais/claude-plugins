---
name: dama-dmbok-governanca-dados
description: >
  Aplica os princípios de Governança de Dados do DAMA-DMBOK2 (capítulo 3) — o núcleo que coordena as
  demais áreas de gestão de dados — em qualquer setor de negócio e qualquer estrutura organizacional. Use
  esta skill sempre que o usuário pedir para desenhar um programa de governança de dados, definir papéis
  de data steward/data owner, criar políticas e princípios de dados, montar um conselho ou comitê de
  governança, priorizar iniciativas de gestão de dados, ou avaliar a maturidade de governança de uma
  organização. Aplique também quando pedirem para "estruturar a governança de dados", "definir quem é
  dono desse dado" ou "criar um comitê de dados". Use em conjunto com as demais skills `dama-dmbok-*`,
  já que a governança orienta e integra todas as outras áreas do DAMA-DMBOK2.
---

# DAMA-DMBOK2 — Governança de Dados (Capítulo 3)

Esta skill traduz e aplica o capítulo de Governança de Dados do DAMA-DMBOK2 de forma genérica, para
qualquer pessoa responsável por estruturar como uma organização toma decisões sobre dados, independente
do setor de negócio ou do porte da organização.

Governança de Dados ocupa uma posição diferente das outras 10 áreas do DAMA-DMBOK2: no framework, ela é
o núcleo que coordena as demais (Arquitetura, Modelagem, Armazenamento e Operações, Segurança,
Integração, Documentos e Conteúdo, Dados de Referência e Mestres, Data Warehousing e BI, Metadados e
Qualidade de Dados). Ao aplicar qualquer uma das outras skills `dama-dmbok-*`, considere se a decisão em
questão precisa de patrocínio, política ou responsável formal — isso é trabalho de governança, mesmo
quando a pergunta parece puramente técnica.

## Definição (DMBOK2)

O exercício de autoridade, controle e tomada de decisão compartilhada (planejamento, monitoramento e
aplicação) sobre a gestão dos ativos de dados.

Todas as organizações tomam decisões sobre dados, com ou sem uma função formal de governança. As que
estabelecem um programa formal exercem essa autoridade com mais intencionalidade e conseguem extrair mais
valor de seus ativos de dados.

Governança de Dados é diferente de governança de TI. Governança de TI decide sobre investimentos,
portfólio de aplicações e arquitetura técnica; Governança de Dados foca exclusivamente na gestão dos
dados como ativo — quem decide o quê sobre os dados, e como as pessoas e processos devem se comportar em
relação a eles.

## Drivers de negócio

Os drivers mais comuns para governança de dados se agrupam em dois eixos:

**Redução de risco**
- Gestão geral de risco: supervisão dos riscos que os dados representam para finanças ou reputação.
- Segurança de dados: proteção dos ativos de dados quanto a disponibilidade, usabilidade, integridade,
  consistência, auditabilidade e segurança.
- Privacidade: controle de informações privadas/confidenciais/pessoais por meio de política e
  monitoramento de conformidade.

**Melhoria de processos**
- Conformidade regulatória: capacidade de responder de forma eficiente e consistente a requisitos
  regulatórios.
- Melhoria de qualidade de dados: contribuir para performance de negócio tornando os dados mais
  confiáveis.
- Gestão de metadados: estabelecer um glossário de negócio para definir e localizar dados na organização.
- Eficiência em projetos: melhorias no ciclo de desenvolvimento para reduzir dívida técnica de dados.
- Gestão de fornecedores: controle de contratos que envolvem dados (armazenamento em nuvem, compra de
  dados externos, terceirização de operações de dados).

Governança de dados não é um fim em si mesma — precisa se alinhar diretamente à estratégia
organizacional. Quanto mais claramente ela ajuda a resolver problemas reais da organização, maior a chance
de as pessoas mudarem comportamentos e adotarem as práticas de governança.

## Objetivos e princípios

**Objetivo**: viabilizar que a organização gerencie dados como um ativo, fornecendo princípios, política,
processos, framework operacional, métricas e supervisão para orientar as atividades de gestão de dados em
todos os níveis. Um programa de governança precisa ser:

- **Sustentável**: governança de dados não é um projeto com fim definido — é um processo contínuo que
  exige comprometimento organizacional. Isso não significa necessariamente grandes reestruturações; significa
  gerenciar a mudança de forma que se sustente além da implementação inicial.
- **Incorporado (embedded)**: governança não é um processo à parte. Suas atividades precisam ser
  incorporadas aos métodos de desenvolvimento de software, ao uso de dados para analytics, à gestão de
  dados mestres e à gestão de risco — não um comitê isolado do trabalho real.
- **Mensurado**: governança bem-feita tem impacto financeiro positivo, mas demonstrar esse impacto exige
  entender o ponto de partida e planejar melhoria mensurável.

**Princípios**:

- **Liderança e estratégia**: governança de dados bem-sucedida começa com liderança visionária e
  comprometida. As atividades de gestão de dados são guiadas por uma estratégia de dados, que por sua vez
  deriva da estratégia de negócio da organização.
- **Orientada a negócio**: governança de dados é um programa de negócio — e, como tal, deve governar
  decisões de TI relacionadas a dados tanto quanto governa a interação do negócio com os dados.
- **Responsabilidade compartilhada**: em todas as áreas de conhecimento de gestão de dados, a governança é
  responsabilidade compartilhada entre data stewards de negócio e profissionais técnicos de gestão de
  dados.
- **Multicamadas**: governança de dados acontece tanto em nível corporativo quanto local, e frequentemente
  em níveis intermediários.
- **Baseada em framework**: como as atividades de governança exigem coordenação entre áreas funcionais, o
  programa precisa estabelecer um framework operacional que defina responsabilidades e interações.
- **Baseada em princípios**: princípios orientadores são a base das atividades e, especialmente, das
  políticas de governança. É melhor articular um conjunto central de princípios antes de escrever
  políticas — políticas escritas sem princípios tendem a resolver apenas problemas pontuais.

## Conceitos essenciais

### Organização orientada a dados
Uma organização data-centric trata dados (não apenas aplicações ou processos) como um dos seus ativos
mais críticos, com práticas de gestão formalizadas — independente de já possuir uma estrutura de
governança madura.

### Modelos de operação de governança
Governança de dados pode operar de forma **centralizada** (uma autoridade única define regras para toda a
organização), **descentralizada/não-invasiva** (a governança se apoia nas estruturas de decisão já
existentes, sem criar burocracia paralela) ou **híbrida** (padrões e políticas centrais, execução
descentralizada por área de negócio). Não existe modelo universalmente correto — a escolha depende da
cultura e maturidade da organização.

### Curadoria de dados (Data Stewardship)
É o termo mais comum para descrever a responsabilidade e a responsabilização (accountability) por dados e
pelos processos que garantem seu controle e uso efetivos. Pode ser formalizada em cargo ou exercida de
forma menos formal por quem já ajuda a organização a extrair valor dos dados. As atividades típicas de um
data steward incluem: criar e manter metadados centrais (glossário de negócio), documentar regras e
padrões de negócio, gerenciar problemas de qualidade de dados, e executar no dia a dia as políticas e
iniciativas de governança.

### Tipos de data steward
- **Chief Data Steward**: pode presidir órgãos de governança de dados ou atuar como CDO em uma estrutura
  de governança virtual/distribuída.
- **Executive Data Steward**: gestor sênior que participa de um conselho de governança de dados.
- **Enterprise Data Steward**: supervisiona um domínio de dados através de múltiplas funções de negócio.
- **Business Data Steward**: profissional de negócio, geralmente especialista reconhecido no assunto,
  responsável por um subconjunto de dados.
- **Data Owner**: um business data steward com autoridade formal de aprovação sobre decisões relativas a
  seu domínio de dados.
- **Technical Data Steward**: profissional técnico (integração, DBA, BI, qualidade de dados, metadados)
  atuando dentro de uma área de conhecimento específica.
- **Coordinating Data Steward**: lidera e representa equipes de stewards de negócio e técnicos nas
  discussões entre times e com os executive data stewards.

Como o próprio DMBOK2 observa: os melhores data stewards costumam ser "encontrados", não "criados do
zero" — em geral já existem pessoas exercendo esse papel informalmente antes de qualquer programa formal.
Formalizar a responsabilidade reconhece esse trabalho e permite que ele seja mais eficaz.

### Políticas de dados
Diretrizes que codificam princípios e intenção de gestão em regras fundamentais sobre criação, aquisição,
integridade, segurança, qualidade e uso de dados. Políticas descrevem o "o quê" da governança; padrões e
procedimentos descrevem o "como". Devem ser relativamente poucas, diretas e objetivas — excesso de
políticas extensas tende a não ser seguido na prática.

### Valoração de ativos de dados
Processo de entender e calcular o valor econômico dos dados para a organização — ferramenta importante
para justificar investimento em governança perante lideranças que enxergam a função apenas como custo
adicional.

## Atividades principais

1. **Definir a Governança de Dados para a organização**: desenvolver a estratégia de governança, avaliar
   prontidão organizacional, alinhar com o negócio, desenvolver pontos de contato organizacionais.
2. **Definir a estratégia de Governança de Dados**: definir o framework operacional, desenvolver
   objetivos/princípios/políticas, viabilizar (underwrite) projetos de gestão de dados, engajar gestão de
   mudança, gerenciar problemas, avaliar requisitos regulatórios.
3. **Implementar a Governança de Dados**: patrocinar padrões e procedimentos, desenvolver o glossário de
   negócio, coordenar com grupos de arquitetura, patrocinar a valoração de ativos de dados.
4. **Incorporar (embed) a Governança de Dados** ao trabalho contínuo da organização.

Ferramentas típicas: presença online/website de governança, ferramentas de glossário de negócio,
ferramentas de workflow, ferramentas de gestão de documentos, scorecards de governança de dados. Métricas
típicas: conformidade com políticas regulatórias e internas, valor gerado, efetividade, sustentabilidade
do programa.

## Princípios práticos de aplicação

- **Não comece pela estrutura organizacional — comece pelo problema de negócio que a governança resolve.**
  Um programa de governança apresentado como "mais uma camada de aprovação" tende a ser rejeitado pela
  liderança; um programa apresentado como solução para um problema já reconhecido (dado ruim, retrabalho,
  risco regulatório) tem muito mais chance de adoção.
- **Formalize os data stewards que já existem antes de criar cargos novos.** Em praticamente toda
  organização já há pessoas exercendo função de curadoria informal de dados — identificá-las e dar
  reconhecimento formal costuma ser mais rápido e mais aceito do que impor uma estrutura nova de fora para
  dentro.
- **Distinga claramente política de padrão/procedimento.** Política define o que deve ou não deve
  acontecer com os dados; padrão e procedimento definem como isso é operacionalizado. Confundir os dois
  níveis gera políticas longas demais para serem seguidas ou padrões técnicos sem respaldo de decisão de
  negócio.
- **Todo data owner deve ter autoridade real de decisão sobre seu domínio**, não apenas o título. Um
  "dono" sem autoridade prática para aprovar ou vetar mudanças no seu domínio de dados é apenas um nome em
  um documento.
- **Conecte governança às demais áreas de gestão de dados de forma explícita.** Um modelo de dados sem
  data steward responsável, uma integração sem política de compartilhamento aprovada, ou uma métrica de
  qualidade sem dono de negócio — todos esses são sintomas de governança ausente disfarçados de problema
  técnico.
- **Meça e comunique valor, não apenas conformidade.** Um programa de governança que só reporta violações
  de política tende a ser visto como controle burocrático; um que também demonstra valor gerado (redução
  de retrabalho, decisões mais rápidas, menor risco) sustenta patrocínio de longo prazo.

## Checklist de diagnóstico

- Existe uma estratégia de governança de dados formalmente alinhada à estratégia de negócio, ou a
  governança existe apenas como documento de política sem uso prático?
- Cada domínio de dados crítico tem um data owner com autoridade real de decisão?
- Existem políticas de dados formalizadas, claras e em número gerenciável — ou uma coleção extensa de
  documentos que ninguém consulta?
- O programa de governança tem patrocínio executivo visível, ou depende apenas do esforço de uma área
  técnica isolada?
- As demais áreas de gestão de dados (arquitetura, qualidade, segurança, metadados etc.) têm ponto de
  conexão claro com a estrutura de governança, ou operam de forma desconectada?
- Existem métricas que demonstrem valor gerado pela governança, além de métricas de conformidade?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 3,
Data Governance.
