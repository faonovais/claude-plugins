---
name: dama-dmbok-armazenamento-operacoes
description: >
  Aplica os princípios de Armazenamento e Operações de Dados do DAMA-DMBOK2 (capítulo 6) para decisões
  sobre gestão de banco de dados, disponibilidade, performance, continuidade de negócio e ciclo de vida
  operacional de dados, em qualquer setor e qualquer tecnologia de banco de dados. Use esta skill sempre
  que o usuário pedir para avaliar performance de banco de dados, definir estratégia de backup/recovery,
  planejar migração ou versionamento de dados, revisar processos de administração de banco de dados
  (DBA), definir política de ambientes (desenvolvimento/homologação/produção), ou discutir gestão de
  dados de teste. Aplique também quando pedirem para "revisar a operação do banco" ou "definir SLA de
  disponibilidade dos dados".
---

# DAMA-DMBOK2 — Armazenamento e Operações de Dados (Capítulo 6)

Esta skill traduz e aplica o capítulo de Armazenamento e Operações de Dados do DAMA-DMBOK2 de forma
genérica, para qualquer pessoa responsável por manter dados armazenados, disponíveis e íntegros,
independente do setor de negócio ou da tecnologia de banco de dados.

## Definição (DMBOK2)

O design, implementação e suporte de dados armazenados, com o objetivo de maximizar seu valor ao longo de
todo o ciclo de vida.

## Objetivos

1. Gerenciar a disponibilidade dos dados ao longo de todo o ciclo de vida.
2. Garantir a integridade dos ativos de dados.
3. Gerenciar a performance das transações de dados.

## Princípios orientadores

- **Identificar e agir sobre oportunidades de automação.** Automatize processos de desenvolvimento e
  operação de banco de dados para reduzir erros, retrabalho e o impacto de cada ciclo de mudança —
  isso viabiliza abordagens ágeis/iterativas em vez de ciclos de mudança lentos e manuais.
- **Construir pensando em reuso.** Desenvolva e promova o uso de objetos de dados reutilizáveis e
  abstraídos, evitando que aplicações fiquem fortemente acopladas ao esquema físico do banco (o chamado
  "descasamento de impedância objeto-relacional"). O objetivo é tornar o uso do banco o mais simples e
  seguro possível para quem consome.
- **Entender e aplicar boas práticas com bom senso.** Padrões de banco de dados devem ser promovidos como
  requisito, mas com flexibilidade para desvios justificados — padrão nunca deve ser motivo de travar um
  projeto sem alternativa.
- **Conectar padrões de banco a requisitos de suporte.** Acordos de nível de serviço (SLA) devem refletir
  claramente a divisão de responsabilidade entre quem administra o banco e quem desenvolve sobre ele,
  evitando uma postura de "tudo ou nada" em relação a padrões.
- **Definir expectativas para o papel de administração de dados desde o início do projeto.** Envolver
  quem administra o banco já na fase de definição do projeto melhora comunicação e evita retrabalho
  posterior.

## Conceitos essenciais

### Ciclo de vida de dados
Dados passam por criação/aquisição, armazenamento, uso, arquivamento e eventual descarte. Cada fase exige
controles próprios de disponibilidade, integridade e performance — tratar todas as fases da mesma forma
(ex: manter tudo "quente" indefinidamente) é ineficiente e caro.

### Tipos de arquitetura e processamento de banco de dados
Bancos podem ser otimizados para processamento transacional (OLTP, muitas transações pequenas e
concorrentes, forte necessidade de integridade referencial) ou analítico (OLAP/analítico, poucas consultas
grandes, otimizadas para leitura). Misturar as duas cargas no mesmo ambigo sem separação arquitetural é
uma causa comum de degradação de performance e de conflito operacional.

### Ambientes de banco de dados
Separação entre ambientes de desenvolvimento, teste/homologação e produção é uma prática essencial de
governança operacional — mudanças estruturais devem ser testadas em ambientes inferiores antes de ir para
produção, com script versionado e reprodutível, nunca alteração manual direta em produção.

### Gestão de dados de teste
Dados de teste devem ser representativos o suficiente para validar mudanças, mas sem expor dados sensíveis
de produção sem mascaramento/anonimização — isso conecta diretamente com a skill
`dama-dmbok-seguranca-dados`.

## Atividades principais

1. **Gerenciar a tecnologia de banco de dados**: entender, avaliar, monitorar e gerenciar continuamente a
   tecnologia de banco de dados utilizada.
2. **Gerenciar operações de banco de dados**: entender requisitos, planejar continuidade de negócio,
   desenvolver instâncias, gerenciar performance, gerenciar dados de teste e gerenciar migração de dados.

Técnicas recomendadas: testar mudanças em ambientes inferiores antes de produção; usar convenções de
nomenclatura física padronizadas; usar scripts versionados para toda mudança estrutural (nunca alteração
manual direta).

## Governança de armazenamento e operações

- **Métricas de armazenamento, performance, operação e serviço** devem ser monitoradas continuamente, não
  apenas quando há incidente.
- **Rastreamento de ativos de informação**: manter inventário atualizado de onde os dados residem
  fisicamente e quem é responsável por cada base.
- **Auditorias e validação de dados**: verificações periódicas de integridade e conformidade dos dados
  armazenados em relação às regras de negócio esperadas.

## Princípios práticos de aplicação

- **Automatize a implantação de mudanças estruturais.** Scripts de mudança versionados e reproduzíveis
  substituem alterações manuais — isso é auditabilidade e redução de erro operacional, não luxo de
  engenharia.
- **Separe cargas transacionais de cargas analíticas em ambientes distintos.** Rodar consultas analíticas
  pesadas contra o mesmo banco que sustenta a operação transacional do dia a dia é uma causa recorrente de
  lentidão percebida pelo negócio.
- **Trate backup, recovery e continuidade como requisito de negócio, não como tarefa técnica isolada.**
  O tempo de recuperação aceitável (RTO) e a perda de dados aceitável (RPO) devem ser definidos junto com
  o negócio, não decididos unilateralmente pela área técnica.
- **Nunca use dados de produção não mascarados em ambientes de teste/desenvolvimento** quando houver
  qualquer dado sensível ou pessoal envolvido.
- **Considere o custo operacional real de manter dados "quentes"** (alta disponibilidade, replicação) para
  dados que raramente são acessados — arquivamento é uma decisão de arquitetura, não apenas de espaço em
  disco.

## Checklist de diagnóstico

- Existe separação clara entre ambientes de desenvolvimento, teste e produção, com processo formal de
  promoção de mudanças?
- Mudanças estruturais em banco de dados são feitas via script versionado, ou há alteração manual direta
  em produção?
- Cargas transacionais e analíticas competem pelos mesmos recursos de banco, ou estão desacopladas?
- RTO e RPO estão definidos e testados, ou a estratégia de backup/recovery nunca foi validada na prática?
- Dados sensíveis em ambientes não produtivos estão mascarados/anonimizados?
- Existem métricas de performance e disponibilidade monitoradas continuamente, com alerta proativo?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 6,
Data Storage and Operations.
