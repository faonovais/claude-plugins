# claude-plugins

Marketplace de plugins e skills para o Claude (Claude Code / Cowork), mantido por
Fábio Novais.

## Instalação

```bash
claude plugin marketplace add faonovais/claude-plugins
claude plugin install storytelling-com-dados@faonovais-claude-plugins
```

Ou, dentro do Claude Code / Cowork:

```
/plugin marketplace add faonovais/claude-plugins
/plugin install storytelling-com-dados@faonovais-claude-plugins
```

## Plugins

- [`storytelling-com-dados`](./storytelling-com-dados) — princípios do livro *Storytelling com Dados* (Cole Nussbaumer Knaflic) aplicados à criação e revisão de apresentações, gráficos e dashboards. Skills: `storytelling-apresentacao`, `storytelling-grafico`, `storytelling-dashboard`.

## Estrutura

Catálogo definido em [`.claude-plugin/marketplace.json`](./.claude-plugin/marketplace.json).
Cada plugin listado ali vive em sua própria pasta na raiz do repositório, com o formato
padrão `.claude-plugin/plugin.json` + `skills/`.
