---
name: dama-dmbok-qualidade-dados
description: >
  Aplica os princípios de Qualidade de Dados do DAMA-DMBOK2 (capítulo 13) para definir estratégia,
  medir, monitorar e melhorar a qualidade de dados, em qualquer setor de negócio. Use esta skill sempre
  que o usuário pedir para avaliar a qualidade de um conjunto de dados, definir dimensões e regras de
  qualidade de dados, fazer profiling de dados, investigar causa raiz de um problema de dados, definir
  métricas de qualidade de dados, ou desenhar um programa de qualidade de dados. Aplique também quando
  pedirem para "verificar se esses dados estão certos" ou "por que esse número está errado no relatório".
---

# DAMA-DMBOK2 — Qualidade de Dados (Capítulo 13)

Esta skill traduz e aplica o capítulo de Qualidade de Dados do DAMA-DMBOK2 de forma genérica, para
qualquer pessoa responsável por garantir que dados sejam adequados ao uso pretendido, independente do
setor de negócio.

## Definição (DMBOK2)

Planejamento, implementação e controle de atividades que aplicam técnicas de gestão de qualidade a dados,
de forma a garantir que estejam aptos para consumo e atendam às necessidades dos consumidores de dados.

## Objetivos

1. Desenvolver uma abordagem governada para tornar os dados adequados ao propósito, com base nos
   requisitos dos consumidores de dados.
2. Definir padrões, requisitos e especificações para controles de qualidade de dados como parte do ciclo
   de vida do dado.
3. Definir e implementar processos para medir, monitorar e reportar níveis de qualidade de dados.
4. Identificar e defender oportunidades de melhoria de qualidade de dados, por meio de melhorias de
   processo e sistema.

## Princípios orientadores

- **Criticidade**: um programa de qualidade de dados deve focar nos dados mais críticos para a
  organização e seus clientes. Prioridades de melhoria devem se basear na criticidade do dado e no nível
  de risco caso o dado esteja incorreto — não é possível (nem necessário) tratar tudo com a mesma
  prioridade.
- **Gestão de ciclo de vida**: a qualidade do dado deve ser gerenciada ao longo de todo o ciclo de vida,
  da criação/aquisição ao descarte, incluindo a movimentação do dado entre sistemas (cada elo da cadeia de
  dados deve garantir que sua saída tenha qualidade).
- **Prevenção**: o foco de um programa de qualidade de dados deve ser prevenir erros e condições que
  reduzem a usabilidade do dado — não apenas corrigir registros já com problema.
- **Remediação de causa raiz**: melhorar a qualidade de dados vai além de corrigir erros pontuais.
  Problemas de qualidade devem ser entendidos e tratados em sua causa raiz, não apenas em seus sintomas —
  como essas causas costumam estar relacionadas a desenho de processo ou de sistema, a melhoria
  frequentemente exige mudança de processo, não apenas limpeza de dados.
- **Governança**: atividades de governança de dados devem apoiar o desenvolvimento de dados de alta
  qualidade, e atividades de qualidade de dados devem apoiar e sustentar um ambiente de dados governado —
  as duas funções se reforçam mutuamente.
- **Orientado a padrões**: todos os stakeholders do ciclo de vida do dado têm requisitos de qualidade.
  Sempre que possível, esses requisitos devem ser definidos como padrões e expectativas mensuráveis contra
  os quais a qualidade pode ser medida.
- **Medição objetiva e transparência**: níveis de qualidade de dados devem ser medidos de forma objetiva e
  consistente. Metodologia de medição deve ser compartilhada com os stakeholders, já que eles são os
  árbitros finais da qualidade.
- **Incorporado aos processos de negócio**: donos de processo de negócio são responsáveis pela qualidade
  dos dados produzidos por seus processos e devem fazer cumprir os padrões de qualidade nesses processos.
- **Aplicado sistematicamente**: donos de sistema devem aplicar requisitos de qualidade de dados de forma
  sistemática (via regras automatizadas), não apenas por revisão manual esporádica.
- **Conectado a acordos de nível de serviço**: reporte de qualidade de dados e gestão de problemas devem
  estar incorporados a SLAs formais.

## Conceitos essenciais

### Dimensões de qualidade de dados
Uma dimensão de qualidade é uma característica mensurável do dado. Não existe um conjunto único e
universalmente aceito de dimensões, mas as mais consolidadas incluem: **exatidão** (o dado reflete
corretamente a realidade), **completude** (todos os dados esperados estão presentes), **consistência**
(o dado é representado de forma uniforme dentro e entre conjuntos de dados), **integridade** (ausência de
órfãos/duplicatas, integridade referencial preservada), **razoabilidade** (o padrão do dado faz sentido
frente às expectativas), **atualidade/tempestividade** (o dado está atualizado no momento em que é
necessário), **unicidade** (nenhuma entidade está duplicada) e **validade** (o dado está em conformidade
com o domínio de valores esperado — formato, tipo, faixa).

Definir quais dimensões medir para cada conjunto de dados crítico é uma decisão de negócio, não uma
aplicação automática de todas as dimensões a todos os dados.

### Profiling de dados
Análise estatística e estrutural de um conjunto de dados (distribuição de valores, nulos, duplicatas,
padrões) para entender seu estado real antes de definir regras de qualidade — muitas vezes revela
problemas que ninguém suspeitava existir.

### Causas comuns de problemas de qualidade de dados
Falta de padronização na entrada de dados, ausência de validação no ponto de captura, integrações sem
tratamento de erro, mudanças de sistema não comunicadas, e ausência de responsável de negócio pela
qualidade do dado em sua origem.

## Atividades principais

1. **Definir dados de alta qualidade**: o que "qualidade" significa para os consumidores desse dado
   específico.
2. **Definir estratégia de qualidade de dados**.
3. **Identificar dados críticos e regras de negócio** aplicáveis.
4. **Realizar avaliação inicial de qualidade de dados** (profiling, identificação e priorização de
   problemas, análise de causa raiz).
5. **Identificar e priorizar melhorias**, com base em impacto de negócio.
6. **Definir metas de melhoria de qualidade de dados**.
7. **Desenvolver e implantar operações de qualidade de dados**: procedimentos operacionais, correção de
   defeitos, medição e monitoramento contínuos, reporte de níveis e achados.

## Governança e métricas de qualidade de dados

- **Política de qualidade de dados**: formaliza papéis, responsabilidades e expectativas mínimas de
  qualidade.
- **Métricas eficazes**: devem ser específicas, mensuráveis e conectadas a impacto de negócio real — não
  métricas genéricas de "% de qualidade" sem contexto de uso.
- **Controle estatístico de processo**: uso de técnicas estatísticas para monitorar variação e detectar
  desvios de qualidade antes que se tornem problemas graves.
- **Análise de causa raiz**: processo estruturado para ir além do sintoma e identificar a origem real de
  um problema recorrente de qualidade.

## Princípios práticos de aplicação

- **Não tente medir qualidade de tudo ao mesmo tempo.** Comece pelos dados mais críticos para as decisões
  de negócio mais importantes — critérios de criticidade e risco devem guiar a priorização.
- **Trate cada problema de qualidade como sintoma até provar o contrário.** Corrigir o registro errado sem
  investigar a causa raiz (processo, integração, ausência de validação) garante que o mesmo problema volte.
- **Qualidade de dados não é responsabilidade exclusiva de quem "cuida do banco".** O dono do processo de
  negócio que originou o dado é responsável por sua qualidade na fonte.
- **Prefira prevenção (validação na entrada, regra automatizada) a correção retroativa.** Corrigir dados
  já processados é sistematicamente mais caro do que impedir a entrada do erro.
- **Toda regra de qualidade de dados deve ser conectada a um impacto de negócio explícito** ("por que essa
  regra importa"), não apenas a uma verificação técnica isolada — isso é o que sustenta a priorização de
  investimento em qualidade ao longo do tempo.

## Checklist de diagnóstico

- Existem dimensões de qualidade definidas e medidas para os dados críticos da organização, ou a qualidade
  é avaliada de forma informal/reativa?
- Problemas de qualidade recorrentes têm análise de causa raiz documentada, ou apenas são corrigidos
  pontualmente cada vez que aparecem?
- Existe processo de profiling de dados antes de novas integrações ou migrações?
- Regras de qualidade de dados são aplicadas de forma automatizada e sistemática, ou dependem de revisão
  manual?
- Existe um dono de negócio responsável pela qualidade de cada conjunto de dados crítico?
- Métricas de qualidade de dados são reportadas regularmente e conectadas a impacto de negócio?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 13,
Data Quality.
