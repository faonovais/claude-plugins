# claude-plugins

Marketplace de plugins e skills para o Claude (Claude Code / Cowork), mantido por
Fábio Novais.

## Instalação

```bash
claude plugin marketplace add faonovais/claude-plugins
claude plugin install storytelling-com-dados@faonovais-claude-plugins
claude plugin install dama-dmbok2@faonovais-claude-plugins
```

Ou, dentro do Claude Code / Cowork:

```
/plugin marketplace add faonovais/claude-plugins
/plugin install storytelling-com-dados@faonovais-claude-plugins
/plugin install dama-dmbok2@faonovais-claude-plugins
```

## Plugins

- [`storytelling-com-dados`](./storytelling-com-dados) — princípios do livro *Storytelling com Dados* (Cole Nussbaumer Knaflic) aplicados à criação e revisão de apresentações, gráficos e dashboards. Skills: `storytelling-apresentacao`, `storytelling-grafico`, `storytelling-dashboard`.
- [`dama-dmbok2`](./damma-dmbok2) — princípios do *DAMA-DMBOK2* (Data Management Body of Knowledge, 2ª edição) aplicados à gestão de dados de qualquer organização: Governança de Dados (núcleo) e as 10 áreas funcionais que ela coordena. Skills: `dama-dmbok-governanca-dados`, `dama-dmbok-arquitetura-dados`, `dama-dmbok-modelagem-dados`, `dama-dmbok-armazenamento-operacoes`, `dama-dmbok-seguranca-dados`, `dama-dmbok-integracao-interoperabilidade`, `dama-dmbok-documentos-conteudo`, `dama-dmbok-dados-referencia-mestres`, `dama-dmbok-dw-bi`, `dama-dmbok-metadados`, `dama-dmbok-qualidade-dados`.

## Estrutura

Catálogo definido em [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json).
Cada plugin listado ali vive em sua própria pasta na raiz do repositório, com o formato
padrão `.claude-plugin/plugin.json` + `skills/`.
