# dama-dmbok2

Plugin Claude que aplica, em português, os princípios das áreas de conhecimento do **DAMA-DMBOK2**
(*Data Management Body of Knowledge*, 2ª edição, DAMA International, 2017) — a arquitetura de referência
para gestão de dados organizada ao redor da Governança de Dados.

Cada área de conhecimento tem uma skill dedicada. As skills são genéricas: aplicam-se a qualquer setor de
negócio e qualquer stack tecnológico, focando em princípios e processos, não em ferramentas específicas.

## Componentes

| Skill | Área do DAMA-DMBOK2 (capítulo) |
|---|---|
| `dama-dmbok-governanca-dados` | Data Governance — núcleo (cap. 3) |
| `dama-dmbok-arquitetura-dados` | Data Architecture (cap. 4) |
| `dama-dmbok-modelagem-dados` | Data Modeling and Design (cap. 5) |
| `dama-dmbok-armazenamento-operacoes` | Data Storage and Operations (cap. 6) |
| `dama-dmbok-seguranca-dados` | Data Security (cap. 7) |
| `dama-dmbok-integracao-interoperabilidade` | Data Integration and Interoperability (cap. 8) |
| `dama-dmbok-documentos-conteudo` | Document and Content Management (cap. 9) |
| `dama-dmbok-dados-referencia-mestres` | Reference and Master Data (cap. 10) |
| `dama-dmbok-dw-bi` | Data Warehousing and Business Intelligence (cap. 11) |
| `dama-dmbok-metadados` | Metadata Management (cap. 12) |
| `dama-dmbok-qualidade-dados` | Data Quality (cap. 13) |

Cada `SKILL.md` traz: definição da área segundo o DMBOK2, objetivos e princípios orientadores do
framework, conceitos essenciais, atividades principais, princípios práticos de aplicação e um checklist de
diagnóstico.

## Setup

Nenhuma configuração ou variável de ambiente é necessária — as skills são conteúdo de conhecimento
(markdown), sem dependência de MCP servers, hooks ou scripts externos.

## Uso

As skills disparam automaticamente quando o pedido do usuário corresponde à área de conhecimento (ex:
"desenhar um modelo de dados", "definir estratégia de qualidade de dados", "revisar segurança de acesso a
dados"). Também podem ser invocadas diretamente pelo nome, por exemplo:
`/dama-dmbok2:dama-dmbok-qualidade-dados`.

## Fonte

DAMA International. *DAMA-DMBOK2: Data Management Body of Knowledge*, 2ª edição, 2017.
