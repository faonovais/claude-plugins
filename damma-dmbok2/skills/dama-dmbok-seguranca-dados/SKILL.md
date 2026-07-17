---
name: dama-dmbok-seguranca-dados
description: >
  Aplica os princípios de Segurança de Dados do DAMA-DMBOK2 (capítulo 7) para definir políticas,
  padrões e controles de acesso, privacidade e confidencialidade de dados, em qualquer setor de negócio.
  Use esta skill sempre que o usuário pedir para definir uma política de segurança de dados, classificar
  dados sensíveis, desenhar controles de acesso (RLS, matriz CRUD), avaliar riscos de exposição de dados,
  discutir mascaramento/anonimização/criptografia de dados, ou avaliar conformidade com regulações de
  privacidade (LGPD, GDPR ou equivalentes). Aplique também quando pedirem para "revisar quem pode acessar
  esses dados" ou "classificar a sensibilidade dessa informação".
---

# DAMA-DMBOK2 — Segurança de Dados (Capítulo 7)

Esta skill traduz e aplica o capítulo de Segurança de Dados do DAMA-DMBOK2 de forma genérica, para
qualquer pessoa responsável por proteger dados contra acesso inadequado, independente do setor de negócio
ou da tecnologia utilizada.

## Definição (DMBOK2)

Definição, planejamento, desenvolvimento e execução de políticas e procedimentos de segurança para
garantir autenticação, autorização, acesso e auditoria apropriados de dados e ativos de informação.

## Objetivos

1. Permitir o acesso apropriado — e prevenir o acesso inapropriado — aos ativos de dados da organização.
2. Garantir conformidade com regulações e políticas de privacidade, proteção e confidencialidade.
3. Garantir que os requisitos de privacidade e confidencialidade de todos os stakeholders sejam atendidos
   e auditados.

## Princípios orientadores

- **Colaboração**: segurança de dados é esforço colaborativo entre administradores de segurança de TI,
  data stewards/governança de dados, auditoria interna/externa e jurídico — não responsabilidade isolada
  de uma única área.
- **Abordagem corporativa**: padrões e políticas de segurança de dados devem ser aplicados de forma
  consistente em toda a organização, não caso a caso por sistema ou projeto.
- **Gestão proativa**: sucesso em segurança de dados depende de ser proativo e dinâmico, engajando todos
  os stakeholders e superando barreiras organizacionais entre segurança da informação, TI, administração
  de dados e áreas de negócio.
- **Responsabilização clara**: papéis e responsabilidades devem ser claramente definidos, incluindo a
  cadeia de custódia dos dados entre organizações e funções.
- **Orientado por metadados**: a classificação de segurança de um dado é parte essencial de sua definição
  — deve estar registrada nos metadados, não apenas na cabeça de quem administra o sistema.
- **Redução de risco pela redução de exposição**: minimize a proliferação de dados sensíveis/confidenciais,
  especialmente em ambientes não produtivos.

## Conceitos essenciais

### Vulnerabilidade, ameaça e risco
Vulnerabilidade é uma fraqueza que pode ser explorada; ameaça é o potencial de exploração dessa fraqueza;
risco é a probabilidade combinada com o impacto de uma ameaça se concretizar. Classificar riscos (por
impacto e probabilidade) é pré-requisito para priorizar investimento em controles.

### Integridade de dados vs. segurança
Integridade garante que o dado não foi alterado indevidamente; segurança garante que apenas quem tem
autorização pode acessar, alterar ou excluir o dado. Os dois conceitos se sobrepõem mas não são idênticos.

### Criptografia e mascaramento/ofuscação
Criptografia protege o dado transformando-o de forma reversível apenas por quem possui a chave.
Mascaramento/ofuscação transforma o dado de forma a preservar seu formato e utilidade para testes ou
análises, sem expor o valor real — essencial para ambientes de desenvolvimento e teste.

### Tipos de segurança e de restrição de dados
Segurança pode ser aplicada em diferentes camadas: rede, aplicação, banco de dados e nível de linha/coluna
(ex: segurança em nível de linha por perfil de usuário ou unidade organizacional). O tipo de controle deve
ser proporcional à sensibilidade do dado e ao perfil de quem acessa.

## Atividades principais

1. **Identificar requisitos de segurança de dados**: levantar exigências regulatórias, contratuais e de
   negócio.
2. **Definir política de segurança de dados**: formalizar regras aplicáveis a toda a organização.
3. **Definir padrões de segurança de dados**: traduzir a política em padrões técnicos e operacionais
   aplicáveis.

Técnicas recomendadas: uso de matriz CRUD (quem pode Criar/Ler/Atualizar/Excluir cada dado); implantação
imediata de patches de segurança; atributos de segurança embutidos nos metadados; necessidades de
segurança já incluídas nos requisitos de projeto desde o início (não como etapa posterior).

## Governança de segurança de dados

Segurança de dados deve estar integrada à Arquitetura de Dados: classificações de segurança fazem parte do
modelo de dados corporativo, não são um controle "por fora" adicionado depois. Visibilidade sobre quem tem
direito de acesso a quais dados (data entitlement) deve ser auditável a qualquer momento.

## Princípios práticos de aplicação

- **Classifique os dados antes de definir controles de acesso.** Sem uma classificação de sensibilidade
  (público, interno, confidencial, restrito), qualquer política de acesso é arbitrária.
- **Segurança em nível de linha (RLS) e outros controles de acesso devem refletir a estrutura
  organizacional real**, não ser um remendo por relatório ou por painel individual.
- **Nunca trate segurança de dados como responsabilidade exclusiva de TI.** Donos de processo de negócio
  devem aprovar quem tem acesso a quê — esse é um princípio de governança, não de tecnologia.
- **Ambientes não produtivos exigem o mesmo rigor de proteção de dados sensíveis que produção**, via
  mascaramento ou geração de dados sintéticos — cópias completas de produção sem tratamento são um risco
  recorrente e evitável.
- **Audite o acesso, não apenas configure-o.** Definir permissões sem revisar periodicamente quem
  efetivamente as usa é uma falha comum de governança de segurança.

## Checklist de diagnóstico

- Existe uma classificação de sensibilidade formal para os dados da organização?
- As políticas de segurança de dados são aplicadas de forma consistente, ou variam por sistema/projeto?
- Existe uma matriz de responsabilidade (quem pode criar/ler/atualizar/excluir) documentada para os dados
  críticos?
- Dados sensíveis em ambientes de teste/desenvolvimento estão mascarados?
- Há um processo de auditoria periódica de quem tem acesso a quê, ou o acesso é concedido e nunca revisto?
- A classificação de segurança está registrada nos metadados do dado, ou depende de conhecimento tácito?

## Fonte
DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017 — Capítulo 7,
Data Security.
