---
name: dama-dmbok-metadados
description: >
  Aplica os princípios de Gestão de Metadados do DAMA-DMBOK2 (capítulo 12) para planejar, arquitetar e
  governar metadados de negócio, técnicos, operacionais e de linhagem, em qualquer setor de negócio. Use
  esta skill sempre que o usuário pedir para criar um glossário de negócio/dicionário de dados, definir
  estratégia de metadados, avaliar um repositório/catálogo de metadados, documentar linhagem e análise de
  impacto, ou padronizar definições e regras de negócio entre sistemas. Aplique também quando pedirem para
  "documentar o que cada campo significa" ou "mapear de onde vem esse dado até onde ele é usado".
---

# DAMA-DMBOK2 — Gestão de Metadados (Capítulo 12)

Esta skill traduz e aplica o capítulo de Gestão de Metadados do DAMA-DMBOK2 de forma genérica, para
qualquer pessoa responsável por documentar e tornar acessível o conhecimento sobre os dados de uma
organização, independente do setor de negócio.

## Definição (DMBOK2)

Planejamento, implementação e controle de atividades que permitem acesso a metadados de alta qualidade e
integrados. Metadados são, de forma simples, "dados sobre dados" — mas na prática incluem qualquer
informação que descreve, explica, localiza ou torna mais fácil recuperar, usar ou gerenciar outros dados.

## Objetivos

1. Prover entendimento organizacional sobre termos de negócio e seu uso.
2. Coletar e integrar metadados de fontes diversas.
3. Prover uma forma padrão de acessar metadados.
4. Garantir qualidade e segurança dos metadados.
5. Estabelecer ou reforçar o uso de padrões técnicos de metadados para viabilizar troca de dados.

## Princípios orientadores

- **Comprometimento organizacional**: obtenha apoio e financiamento da alta gestão para a gestão de
  metadados como parte da estratégia de gerenciar dados como ativo corporativo — sem patrocínio, a
  iniciativa não se sustenta.
- **Estratégia**: desenvolva uma estratégia de metadados que defina como eles serão criados, mantidos,
  integrados e acessados. A estratégia deve orientar os requisitos, definidos antes de avaliar ou comprar
  ferramentas — nunca o contrário.
- **Perspectiva corporativa**: adote uma visão corporativa para garantir extensibilidade futura, mas
  implemente de forma iterativa e incremental.
- **Socialização**: comunique a necessidade de metadados e o propósito de cada tipo — isso estimula o uso
  pelo negócio e, tão importante quanto, a contribuição de conhecimento de negócio.
- **Acesso**: garanta que as pessoas saibam como acessar e usar os metadados disponíveis.
- **Qualidade**: reconheça que metadados são frequentemente produzidos por processos já existentes
  (modelagem de dados, ciclo de desenvolvimento, definição de processos de negócio) e responsabilize os
  donos desses processos pela qualidade dos metadados gerados.
- **Auditoria**: defina, imponha e audite padrões de metadados para simplificar integração e viabilizar
  uso.
- **Melhoria contínua**: crie um mecanismo de feedback para que consumidores possam informar metadados
  incorretos ou desatualizados.

## Conceitos essenciais

### Tipos de metadados
- **Metadados de negócio**: definições de termos, regras de negócio, políticas — a camada que conecta
  dado técnico a significado de negócio.
- **Metadados técnicos**: estrutura física de tabelas/colunas, tipos de dado, formatos, esquemas de banco.
- **Metadados operacionais**: informações sobre execução de processos (horários de carga, volumes
  processados, taxas de erro).
- **Metadados de governança**: papéis, responsabilidades, políticas e regras aplicadas aos dados.

Um mesmo dado normalmente tem representações nas quatro camadas simultaneamente — a maturidade de gestão
de metadados se mede por quão bem essas camadas estão conectadas entre si.

### Linhagem e análise de impacto
Linhagem documenta o caminho de um dado desde a origem até seu uso final. Análise de impacto usa essa
mesma informação na direção oposta: dado uma mudança proposta em uma fonte, identificar tudo o que será
afetado a jusante. Sem metadados de linhagem confiáveis, análise de impacto vira um processo manual, lento
e sujeito a erro — um risco direto para qualquer mudança em produção.

## Atividades principais

1. **Definir a estratégia de metadados**.
2. **Entender os requisitos de metadados** (de usuários de negócio e técnicos).
3. **Definir a arquitetura de metadados**: criar o metamodelo, aplicar padrões, gerenciar os repositórios.
4. **Criar e manter metadados**: integrar, distribuir e entregar metadados continuamente.
5. **Consultar, reportar e analisar metadados**.

## Governança de metadados

- **Controles de processo**: garantir que a criação e manutenção de metadados façam parte do processo
  normal de trabalho (modelagem, desenvolvimento, mudança), não uma tarefa administrativa separada e
  frequentemente ignorada.
- **Documentação das soluções de metadados**: a própria solução de gestão de metadados deve ser
  documentada e mantida.
- **Padrões e diretrizes de metadados**: definidos, comunicados e auditados.
- **Métricas**: cobertura de metadados (scorecard), contribuição ao repositório, uso, qualidade.

## Princípios práticos de aplicação

- **Comece pelo glossário de negócio, não pelo catálogo técnico.** Definições de negócio consistentes
  resolvem mais ambiguidade e retrabalho do que documentação técnica isolada de tabelas e colunas.
- **Metadados não são um projeto com fim — são um processo contínuo acoplado ao ciclo de vida do dado.**
  Uma iniciativa de metadados tratada como projeto único, sem processo de manutenção, fica obsoleta em
  poucos meses.
- **A qualidade do metadado é responsabilidade de quem já produz o processo de origem** (quem modela,
  quem desenvolve, quem define regra de negócio) — não deve ser uma tarefa adicional isolada de
  "documentação" feita depois, por outra pessoa, sem contexto.
- **Priorize metadados de linhagem para os fluxos de dados mais críticos ou mais auditados primeiro.** Não
  é necessário (nem viável) documentar tudo de uma vez — priorize onde a ausência de rastreabilidade gera
  mais risco.
- **Um repositório de metadados sem processo de atualização vira mais um sistema desatualizado.** A
  ferramenta é secundária; o processo de manutenção contínua é o que sustenta o valor.

## Checklist de diagnóstico

- Existe um glossário de negócio com definições consistentes e aprovadas pelos donos de negócio dos
  termos?
- Metadados técnicos (estrutura de tabelas/colunas) estão documentados e conectados às definições de
  negócio correspondentes?
- É possível rastrear a linhagem de um dado crítico da origem até o relatório final sem investigação
  manual extensa?
- Existe processo de manutenção contínua dos metadados, ou eles foram documentados uma vez e nunca mais
  atualizados?
- Os metadados são acessíveis a quem precisa deles (analistas, desenvolvedores, usuários de negócio), ou
  ficam restritos a um grupo técnico?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 12,
Metadata Management.
