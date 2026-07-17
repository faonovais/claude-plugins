---
name: dama-dmbok-modelagem-dados
description: >
  Aplica os princípios de Modelagem e Design de Dados do DAMA-DMBOK2 (capítulo 5) para criar, revisar
  ou avaliar modelos de dados conceituais, lógicos e físicos, em qualquer setor de negócio e com
  qualquer tecnologia de banco de dados. Use esta skill sempre que o usuário pedir para criar um
  modelo de dados/modelo entidade-relacionamento, modelar um esquema dimensional (star schema/floco de
  neve), definir chaves primárias/estrangeiras e cardinalidades, decidir sobre normalização vs.
  desnormalização, revisar convenções de nomenclatura de tabelas e colunas, ou avaliar a qualidade e
  governança de um modelo de dados existente. Aplique também quando pedirem para "desenhar um DER",
  "modelar as dimensões e fatos" ou "revisar o modelo lógico/físico".
---

# DAMA-DMBOK2 — Modelagem e Design de Dados (Capítulo 5)

Esta skill traduz e aplica o capítulo de Modelagem e Design de Dados do DAMA-DMBOK2 de forma genérica,
para qualquer pessoa que precise criar, documentar ou avaliar modelos de dados, independente do setor de
negócio ou da tecnologia de banco de dados usada.

## Definição (DMBOK2)

Modelagem de dados é o processo de descobrir, analisar e delimitar requisitos de dados, e depois
representar e comunicar esses requisitos em uma forma precisa chamada modelo de dados. É um processo
iterativo que tipicamente produz três camadas: modelo conceitual, lógico e físico.

## Objetivo e princípios

**Objetivo:** confirmar e documentar o entendimento de diferentes perspectivas de negócio, gerando
aplicações mais alinhadas aos requisitos atuais e futuros, e criando uma base para iniciativas de maior
escopo (MDM, governança de dados).

A modelagem cumpre três funções que justificam seu custo:

- **Formalização**: um modelo de dados documenta de forma concisa estruturas e relacionamentos,
  permitindo avaliar como regras de negócio afetam os dados (estado atual ou desejado). Definição formal
  impõe disciplina que reduz anomalias de dados.
- **Definição de escopo**: um modelo de dados ajuda a explicar os limites de contexto de dados de um
  pacote, projeto ou sistema existente.
- **Retenção de conhecimento/documentação**: o modelo preserva a memória organizacional sobre um sistema
  ou domínio de negócio, servindo de mapa reutilizável para analistas, modeladores e desenvolvedores.

## Conceitos essenciais

### Os três níveis de modelo
- **Conceitual**: entidades e relacionamentos de negócio, sem detalhes técnicos — comunica-se com
  stakeholders de negócio.
- **Lógico**: atributos completos, chaves, tipos de dado em nível de negócio, ainda independente de SGBD.
- **Físico**: implementação específica em um SGBD — nomes de tabelas/colunas físicas, tipos de dado
  específicos, índices, particionamento.

### Esquemas de modelagem
Os seis esquemas mais usados são: relacional, dimensional, orientado a objetos, baseado em fatos, baseado
em tempo (temporal) e NoSQL (chave-valor, coluna larga, documento, grafo). A escolha do esquema depende do
uso do dado (transacional vs. analítico) e não deve ser decidida por preferência de ferramenta.

### Normalização e desnormalização
Normalização reduz redundância e anomalias de atualização, sendo o padrão para modelos transacionais
(tipicamente até a 3ª forma normal). Desnormalização controlada — como em esquemas dimensionais (star
schema) — otimiza performance de leitura e simplicidade de consumo analítico, ao custo de alguma
redundância gerenciada. A decisão entre normalizar e desnormalizar deve ser explícita e documentada, não
acidental.

### Abstração
Uso de supertipos/subtipos e generalizações para simplificar o modelo e aumentar sua capacidade de
absorver mudanças de negócio sem redesenho estrutural constante.

## Atividades principais

1. **Planejar a modelagem de dados**: definir escopo, abordagem e ferramentas.
2. **Construir o modelo de dados**: criar o modelo conceitual, depois o lógico, depois o físico —
   nessa ordem de refinamento.
3. **Revisar os modelos de dados**: validação por pares e por stakeholders de negócio antes da
   implementação.
4. **Manter os modelos de dados**: versionar e evoluir os modelos junto com o sistema, evitando que o
   modelo documentado fique desatualizado em relação à implementação real.

## Boas práticas (DMBOK2)

**Nomenclatura**: convenções de nomes consistentes e documentadas para entidades, atributos e objetos
físicos (tabelas, colunas, chaves, índices). Nomes devem ser claros para quem consome o dado, não apenas
para quem o modelou. Evite abreviações ambíguas e inconsistência entre camadas (ex: mesmo conceito de
negócio com nomes diferentes no modelo lógico e no físico).

**Design de banco de dados**: decisões físicas (indexação, particionamento, desnormalização) devem ser
rastreáveis a um requisito de performance ou de negócio real — não a hábito ou "achismo" técnico.

## Governança do modelo de dados

A qualidade de um modelo de dados deve ser gerenciada com o mesmo rigor de qualquer outro ativo de dados:
revisão por pares, checklist de completude (todas as entidades têm chave, todos os relacionamentos têm
cardinalidade definida, todos os atributos têm definição de negócio), e métricas de reuso e de
conformidade com os padrões corporativos de nomenclatura.

## Princípios práticos de aplicação

- **O modelo lógico é o contrato entre negócio e tecnologia.** Se o time de negócio não consegue
  entender o modelo, ele não está cumprindo sua função de comunicação — simplifique ou complemente com um
  glossário de negócio (ver skill `dama-dmbok-metadados`).
- **Não pule direto para o modelo físico.** Modelar direto na ferramenta de banco de dados, sem passar
  por conceitual/lógico, tende a herdar as limitações e vieses do sistema de origem em vez de representar
  o domínio de negócio real.
- **Em modelos analíticos (DW/DM), documente explicitamente a escolha do esquema** (estrela, floco de
  neve, Data Vault etc.) e a justificativa — modelagem dimensional bem aplicada (Kimball) prioriza
  usabilidade e performance de consulta sobre normalização estrita.
- **Toda mudança estrutural no modelo físico deve ser rastreável** a uma mudança correspondente no modelo
  lógico/conceitual, para não gerar deriva (drift) entre documentação e implementação real — isso é
  auditabilidade básica.
- **Padronize nomenclatura antes de escalar.** Inconsistência de nomes entre tabelas/colunas de diferentes
  origens é uma das causas mais comuns de retrabalho em integrações e de erro silencioso em relatórios.

## Checklist de diagnóstico

- O modelo tem as três camadas (conceitual, lógico, físico) ou parte direto para o físico?
- Toda entidade tem uma definição de negócio clara e um dono (data steward) responsável por ela?
- As convenções de nomenclatura são consistentes e documentadas entre todas as camadas do modelo?
- A escolha entre normalizar e desnormalizar foi deliberada e documentada, ou é resultado de acidente
  histórico?
- Existe processo de revisão do modelo antes de mudanças estruturais irem para produção?
- O modelo está versionado e atualizado, refletindo o estado real da implementação?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 5,
Data Modeling and Design.
