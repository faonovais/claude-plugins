---
name: dama-dmbok-integracao-interoperabilidade
description: >
  Aplica os princípios de Integração e Interoperabilidade de Dados do DAMA-DMBOK2 (capítulo 8) para
  desenhar e avaliar pipelines de movimentação, transformação e consolidação de dados entre sistemas,
  em qualquer setor e qualquer ferramenta de ETL/ELT. Use esta skill sempre que o usuário pedir para
  desenhar um pipeline de integração de dados, decidir entre ETL e ELT, avaliar latência e replicação de
  dados, desenhar orquestração de fluxo de dados entre sistemas, definir contratos/acordos de
  compartilhamento de dados, ou revisar a linhagem (lineage) de uma integração. Aplique também quando
  pedirem para "integrar esses dois sistemas" ou "desenhar o fluxo de carga de dados".
---

# DAMA-DMBOK2 — Integração e Interoperabilidade de Dados (Capítulo 8)

Esta skill traduz e aplica o capítulo de Integração e Interoperabilidade de Dados (DII) do DAMA-DMBOK2 de
forma genérica, para qualquer pessoa responsável por mover, consolidar ou sincronizar dados entre sistemas,
independente do setor de negócio ou da ferramenta utilizada.

## Definição (DMBOK2)

Gestão da movimentação e consolidação de dados dentro e entre aplicações e organizações.

## Objetivos

1. Disponibilizar dados de forma segura, em conformidade regulatória, no formato e prazo necessários.
2. Reduzir custo e complexidade de manutenção desenvolvendo modelos e interfaces compartilhados.
3. Identificar eventos significativos e disparar automaticamente alertas e ações.
4. Suportar business intelligence, analytics, gestão de dados mestres e eficiência operacional.

## Princípios orientadores

- **Adote uma perspectiva corporativa no desenho, mas implemente de forma iterativa e incremental.**
  Pensar a integração de ponta a ponta evita retrabalho futuro, mas a entrega deve ser fatiada em
  incrementos que gerem valor rapidamente.
- **Equilibre necessidades locais e corporativas**, incluindo suporte e manutenção de longo prazo — uma
  integração ponto a ponto que resolve um problema local pode gerar dívida técnica corporativa.
- **Garanta responsabilidade de negócio sobre o desenho e a atividade de integração.** Especialistas de
  negócio devem participar da definição e alteração de regras de transformação de dados, tanto
  persistentes quanto virtuais — regra de transformação não é decisão puramente técnica.

## Conceitos essenciais

### ETL vs. ELT
Extract-Transform-Load transforma o dado antes de carregá-lo no destino; Extract-Load-Transform carrega o
dado bruto primeiro e transforma no destino, aproveitando o poder de processamento do banco/plataforma
analítica. A escolha depende de volume, latência exigida e onde a governança da regra de transformação
deve residir.

### Latência
Tempo entre a geração do dado na origem e sua disponibilidade no destino. Deve ser definida como requisito
de negócio explícito (batch diário, near real-time, real-time), não decidida por padrão técnico ou por
limitação de ferramenta.

### Modelo canônico / formato de mensagem corporativo
Um formato de troca de dados padronizado e compartilhado entre sistemas reduz o número de mapeamentos
ponto a ponto necessários (de N×N para N mapeamentos contra o padrão). Isso é o principal antídoto contra
a "teia" de integrações não governadas.

### Linhagem de dados (lineage)
Documentação de onde o dado se originou, por onde passou e como foi transformado até chegar ao destino
final. É pré-requisito para auditoria, troubleshooting e confiança no dado.

## Atividades principais

1. **Planejar e analisar**: definir requisitos de integração e ciclo de vida, descobrir dados, documentar
   linhagem, perfilar dados (data profiling), examinar conformidade com regras de negócio.
2. **Desenhar soluções de integração**: desenhar componentes da solução, mapear origem para destino,
   desenhar a orquestração dos dados.
3. **Desenvolver soluções de integração**: construir serviços de dados, orquestração de fluxo, abordagem
   de migração, processamento de eventos complexos; manter os metadados da integração.
4. **Implementar e monitorar**: colocar em produção e monitorar continuamente.

## Governança de integração e interoperabilidade

- **Acordos de compartilhamento de dados**: contratos formais definindo o que é compartilhado, com quem,
  sob quais condições de uso e responsabilidade.
- **Linhagem de dados**: toda integração deve produzir e manter documentação de linhagem, não apenas
  código de transformação.
- **Métricas de integração**: volume e velocidade de entrega, latência, tempo de mercado para mudanças,
  custo e complexidade das soluções, valor entregue.

## Princípios práticos de aplicação

- **Prefira um hub de integração com modelo canônico a integrações ponto a ponto**, mesmo que o hub exija
  investimento inicial maior — o custo de manutenção de N×N integrações cresce mais rápido que o de um hub
  central.
- **Toda regra de transformação de dados deve ter um dono de negócio identificável**, não apenas um
  desenvolvedor que a implementou — isso é rastreabilidade e governança, não apenas boa prática de
  engenharia.
- **Documente a linhagem no momento em que a integração é construída**, não depois. Linhagem reconstruída
  retroativamente é sistematicamente menos confiável.
- **Antes de aumentar a frequência/latência de uma integração**, valide se há um requisito de negócio real
  para isso — integrações em tempo real custam mais em complexidade e infraestrutura do que integrações em
  lote, e nem todo processo de negócio precisa de dado em tempo real.
- **Trate pipelines de integração como software**: versionamento, testes, ambientes separados e revisão de
  código, não scripts ad-hoc mantidos por uma única pessoa.

## Checklist de diagnóstico

- Existe um modelo canônico ou formato padrão de troca de dados, ou cada integração define seu próprio
  formato?
- A latência de cada integração está alinhada a um requisito de negócio explícito e documentado?
- A linhagem de dados está documentada e acessível, ou depende de investigação manual quando surge dúvida?
- Regras de transformação de dados têm um dono de negócio responsável, ou são decisão exclusiva de quem
  programa?
- Existem acordos formais de compartilhamento de dados entre sistemas/áreas/organizações?
- As integrações são versionadas e testadas em ambientes separados antes de produção?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 8,
Data Integration and Interoperability.
