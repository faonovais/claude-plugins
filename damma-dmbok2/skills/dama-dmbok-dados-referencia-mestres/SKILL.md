---
name: dama-dmbok-dados-referencia-mestres
description: >
  Aplica os princípios de Dados de Referência e Dados Mestres (MDM) do DAMA-DMBOK2 (capítulo 10) para
  desenhar governança de entidades compartilhadas (clientes, produtos, unidades organizacionais, tabelas
  de domínio), em qualquer setor de negócio. Use esta skill sempre que o usuário pedir para resolver
  duplicidade cadastral, definir a fonte única da verdade (golden record) para uma entidade, desenhar
  processo de gestão de dados mestres, padronizar tabelas de domínio/referência (códigos, categorias,
  status), ou avaliar estratégia de consolidação de cadastros entre sistemas. Aplique também quando
  pedirem para "unificar os cadastros" ou "definir qual sistema é a fonte oficial desse dado".
---

# DAMA-DMBOK2 — Dados de Referência e Dados Mestres (Capítulo 10)

Esta skill traduz e aplica o capítulo de Dados de Referência e Dados Mestres do DAMA-DMBOK2 de forma
genérica, para qualquer pessoa responsável por governar entidades de dados compartilhadas entre sistemas
e processos, independente do setor de negócio.

## Definição (DMBOK2)

Gestão de dados compartilhados para atender objetivos organizacionais, reduzir riscos associados à
redundância de dados, garantir maior qualidade e reduzir os custos de integração de dados.

## Objetivos

1. Permitir o compartilhamento de ativos de informação entre domínios de negócio e aplicações dentro da
   organização.
2. Fornecer uma fonte autoritativa de dados mestres e de referência reconciliados e com qualidade
   avaliada.
3. Reduzir custo e complexidade por meio de padrões, modelos de dados comuns e padrões de integração.

## Princípios orientadores

- **Dados compartilhados**: dados de referência e mestres devem ser gerenciados de forma que sejam
  compartilháveis por toda a organização — não pertencem a um sistema ou área isoladamente.
- **Propriedade**: dados de referência e mestres pertencem à organização, não a uma aplicação ou
  departamento específico. Por serem amplamente compartilhados, exigem alto nível de curadoria
  (stewardship).
- **Qualidade**: gestão de dados mestres e de referência exige monitoramento contínuo de qualidade e
  governança — não é uma iniciativa "de uma vez só".
- **Curadoria (stewardship)**: data stewards de negócio são responsáveis por controlar e garantir a
  qualidade dos dados de referência.
- **Mudança controlada**: a qualquer momento, os valores de dados mestres devem representar o melhor
  entendimento da organização sobre o que é atual e correto. Regras de correspondência (matching) que
  alteram valores devem ser aplicadas com cautela e supervisão; qualquer identificador unido ou dividido
  deve ser reversível. Mudanças em dados de referência devem seguir processo definido, com aprovação e
  comunicação antes da implementação.
- **Autoridade**: valores de dados mestres devem ser replicados apenas a partir do sistema de registro
  (system of record). Pode ser necessário um sistema de referência para permitir o compartilhamento de
  dados mestres pela organização.

## Conceitos essenciais

### Diferença entre dados mestres e dados de referência
**Dados mestres** representam as entidades de negócio centrais e compartilhadas (ex: cliente, produto,
fornecedor, unidade organizacional) — costumam ser volumosos, mutáveis e centrais aos processos
transacionais. **Dados de referência** são conjuntos de valores usados para categorizar ou qualificar
outros dados (ex: códigos de status, unidades de medida, categorias, códigos de país) — costumam ser
pequenos em volume, relativamente estáveis, e frequentemente definidos por padrões externos (internos ou
de mercado/regulatórios).

### System of record vs. system of reference
O sistema de registro (system of record) é a fonte autoritativa e original de um dado mestre. Um sistema
de referência pode existir para disponibilizar esse dado mestre de forma consolidada a outros sistemas,
sem se tornar ele mesmo uma segunda fonte de verdade divergente.

### Arquitetura de compartilhamento de dados
Padrões técnicos (hub-and-spoke, registry, consolidação central) para tornar dados mestres e de referência
acessíveis de forma consistente por múltiplos sistemas consumidores, minimizando duplicação e divergência.

## Atividades principais

1. **Atividades de MDM**: identificar drivers e requisitos, avaliar fontes de dados, definir abordagem
   arquitetural, modelar os dados, definir processos de curadoria e manutenção, estabelecer políticas de
   governança, implementar serviços de compartilhamento/integração de dados.
2. **Atividades de dados de referência**: validar definições de dados, publicar e manter valores de
   referência e mestres de forma consistente.

## Governança de dados de referência e mestres

- **Acordos de compartilhamento de dados**: formalizam quem pode consumir, alterar e é responsável por
  cada entidade mestre/de referência.
- **Monitoramento de movimentação de dados**: rastrear onde e como dados mestres se propagam pelos
  sistemas, para detectar divergência entre cópias.
- **Gestão de mudança de dados de referência**: qualquer alteração em valores de referência (ex: adicionar,
  descontinuar ou renomear uma categoria) deve seguir processo formal de aprovação e comunicação, dado o
  impacto em cascata sobre todos os sistemas consumidores.

## Princípios práticos de aplicação

- **Resolva a duplicidade na origem, não no relatório.** Se a mesma entidade (cliente, produto, unidade
  organizacional) existe com identificadores diferentes em sistemas diferentes, a reconciliação deve
  acontecer em um processo de MDM governado — não em uma fórmula de `JOIN` improvisada em cada relatório.
- **Defina explicitamente qual sistema é o system of record de cada entidade mestre.** Ambiguidade sobre
  "qual sistema manda" é a causa raiz mais comum de divergência de dados mestres entre sistemas.
- **Tabelas de referência (domínio, status, categorias) merecem o mesmo rigor de governança que dados
  mestres**, apesar do volume pequeno — uma mudança não comunicada em um código de referência quebra
  silenciosamente relatórios e integrações a jusante.
- **Nomeie um data steward de negócio para cada entidade mestre crítica.** Qualidade de dados mestres não
  se sustenta sem um responsável de negócio claramente identificado, mesmo que a implementação técnica
  seja de TI.
- **Antes de investir em uma ferramenta de MDM**, avalie se o problema é de governança/processo (falta de
  dono, falta de processo de mudança) — ferramenta não resolve ausência de processo.

## Checklist de diagnóstico

- Está claro, para cada entidade mestre crítica, qual sistema é a fonte oficial (system of record)?
- Existe processo formal de curadoria (quem aprova criação, alteração e desativação de um registro
  mestre)?
- Duplicidades cadastrais são resolvidas de forma centralizada e governada, ou cada consumidor de dado
  resolve à sua maneira?
- Tabelas de referência têm processo de mudança formal, com comunicação aos sistemas consumidores?
- Existe um data steward de negócio designado para as principais entidades mestres?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 10,
Reference and Master Data.
