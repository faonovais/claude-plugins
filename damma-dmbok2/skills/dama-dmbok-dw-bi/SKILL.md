---
name: dama-dmbok-dw-bi
description: >
  Aplica os princípios de Data Warehousing e Business Intelligence do DAMA-DMBOK2 (capítulo 11) para
  planejar, desenhar e avaliar arquiteturas de data warehouse, data marts e portfólios de BI, em qualquer
  setor de negócio e qualquer ferramenta. Use esta skill sempre que o usuário pedir para desenhar a
  arquitetura de um data warehouse, escolher entre abordagem Inmon (corporate information factory) e
  Kimball (dimensional), planejar a população/carga de um DW, definir o portfólio de relatórios/BI,
  avaliar autosserviço de BI, ou revisar a governança de um ambiente de DW/BI existente. Aplique também
  quando pedirem para "desenhar o data warehouse" ou "estruturar os data marts".
---

# DAMA-DMBOK2 — Data Warehousing e Business Intelligence (Capítulo 11)

Esta skill traduz e aplica o capítulo de Data Warehousing e Business Intelligence do DAMA-DMBOK2 de forma
genérica, para qualquer pessoa responsável por projetar ou avaliar um ambiente de DW/BI, independente do
setor de negócio ou da ferramenta utilizada.

## Definição (DMBOK2)

Planejamento, implementação e processos de controle para fornecer dados de suporte à decisão e apoiar
trabalhadores do conhecimento engajados em reporting, consulta e análise.

## Objetivos

1. Construir e manter o ambiente técnico e os processos técnicos/de negócio necessários para entregar
   dados integrados que suportem funções operacionais, requisitos de compliance e atividades de business
   intelligence.
2. Apoiar e viabilizar análise de negócio eficaz e tomada de decisão por trabalhadores do conhecimento.

## Princípios orientadores

- **Foque em objetivos de negócio.** Garanta que o DW sirva às prioridades organizacionais e resolva
  problemas de negócio reais — não é um exercício técnico de modelagem por si só.
- **Comece com o fim em mente.** Deixe que a prioridade de negócio e o escopo de entrega final de dados
  (na camada de BI) orientem o que é construído no DW, não o contrário.
- **Pense e desenhe globalmente; construa e entregue localmente.** A visão de longo prazo guia a
  arquitetura, mas a entrega deve ser incremental, por projetos ou sprints focados, gerando retorno mais
  imediato.
- **Sumarize e otimize por último, não primeiro.** Construa sobre o dado atômico (no nível de detalhe mais
  granular disponível). Agregação e sumarização servem para atender requisitos de performance, não para
  substituir o detalhe.
- **Promova transparência e autosserviço.** Quanto mais contexto (metadados de todo tipo) for fornecido,
  melhor os consumidores de dados conseguem extrair valor. Mantenha os stakeholders informados sobre os
  dados e os processos que os integram.
- **Construa metadados junto com o warehouse.** A capacidade de explicar o dado é crítica para o sucesso
  do DW — responder "por que essa soma é X", "como isso foi calculado" e "de onde veio o dado" deve estar
  sempre disponível.
- **Colabore.** A iniciativa de DW deve colaborar ativamente com governança de dados, qualidade de dados e
  gestão de metadados — DW/BI não é um silo isolado das outras funções de gestão de dados.
- **Uma solução não serve para todos.** Use as ferramentas e formatos certos para cada grupo de
  consumidores de dados — nem todo consumidor precisa da mesma granularidade ou interface.

## Conceitos essenciais

### Duas abordagens clássicas de arquitetura
**Corporate Information Factory (Inmon)**: constrói um data warehouse corporativo normalizado e
integrado como camada central, do qual data marts departamentais são derivados. Prioriza consistência
corporativa antes da entrega departamental.

**Data Warehouse Dimensional (Kimball)**: define o data warehouse como "uma cópia dos dados transacionais
especificamente estruturada para consulta e análise". Os dados são armazenados em modelo dimensional
(esquema estrela), com tabelas fato (dados quantitativos de processos de negócio) e tabelas dimensão
(atributos descritivos). Múltiplos data marts se integram no nível corporativo por meio de dimensões
compartilhadas ("conformadas"), organizadas em uma matriz de barramento (bus matrix) que mapeia processos
de negócio contra subject areas — uma ferramenta útil para planejar incrementos de desenvolvimento de
forma independente de tecnologia.

Nenhuma das duas abordagens é universalmente superior — a escolha depende da necessidade de consistência
corporativa vs. velocidade de entrega, e organizações frequentemente combinam elementos das duas.

### Tipos de processamento de carga
Cargas podem ser completas (full load, recriando o conjunto de dados) ou incrementais (carregando apenas o
que mudou desde a última carga) — a escolha impacta diretamente performance, janela de processamento e
complexidade do processo de captura de mudanças.

## Atividades principais

1. **Entender requisitos**: levantar necessidades de negócio, escalabilidade, operação, qualidade,
   segurança e acesso.
2. **Definir e manter a arquitetura de DW/BI**.
3. **Desenvolver o data warehouse e os data marts**.
4. **Popular o data warehouse** (processos de carga).
5. **Implementar o portfólio de business intelligence** (relatórios, dashboards, análises).
6. **Manter os produtos de dados** ao longo do tempo.

## Governança de DW/BI

- **Aceite do negócio**: o sucesso de um DW/BI depende de adoção real pelo negócio, não apenas de entrega
  técnica.
- **Satisfação do cliente/usuário**: deve ser medida continuamente, não assumida.
- **Acordos de nível de serviço (SLA)**: para disponibilidade, performance e atualização de dados.
- **Estratégia de reporting**: definição clara de quais relatórios/análises pertencem ao portfólio
  corporativo governado vs. o que é autosserviço departamental.
- **Métricas**: uso, satisfação do usuário, cobertura de subject areas, performance/tempo de resposta.

## Princípios práticos de aplicação

- **O DW não deve ser uma cópia 1:1 do sistema de origem.** A arquitetura dimensional (fatos e dimensões)
  existe justamente para desacoplar a estrutura de consumo analítico da estrutura transacional de origem.
- **Metadados de negócio (definições, regras de cálculo, origem do dado) são parte da entrega do DW, não
  um anexo opcional.** Um DW sem essa camada de explicação gera desconfiança no dado, mesmo que os números
  estejam corretos.
- **Autosserviço de BI precisa de governança, não ausência dela.** Disponibilizar dados brutos sem modelo
  semântico corporativo e sem medidas padronizadas gera múltiplas versões da verdade — o oposto do
  objetivo de um DW corporativo.
- **A escolha entre carga completa e incremental deve considerar volume, janela de processamento
  disponível e necessidade real de histórico** — não deve ser decidida apenas pela facilidade de
  implementação inicial.
- **Priorize entregas incrementais que resolvam um problema de negócio real** antes de tentar modelar o
  data warehouse corporativo completo de uma vez — arquiteturas "big bang" de DW têm alto risco de nunca
  entregar valor.

## Checklist de diagnóstico

- O DW está estruturado em modelo dimensional (fatos/dimensões) ou é um espelho do schema transacional de
  origem?
- Existem dimensões conformadas (compartilhadas) entre os principais processos de negócio, evitando
  definições divergentes da mesma entidade?
- Metadados de negócio (definições, regras de cálculo, origem) estão documentados e acessíveis aos
  consumidores?
- Existe uma camada de modelo semântico corporativo governado, ou cada relatório redefine suas próprias
  medidas?
- A estratégia de carga (completa vs. incremental) está alinhada ao volume de dados e à janela de
  processamento disponível?
- Existem métricas de adoção e satisfação do usuário sendo monitoradas?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 11,
Data Warehousing and Business Intelligence.
