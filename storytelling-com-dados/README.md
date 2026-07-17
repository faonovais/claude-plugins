# storytelling-com-dados

Plugin com os princípios do livro *Storytelling com Dados* (Cole Nussbaumer Knaflic,
Alta Books, 2019) aplicados à criação e revisão de apresentações, gráficos e
dashboards. Genérico: não é específico de nenhum setor, indústria ou ferramenta de BI.

## Componentes

Três skills, cada uma cobrindo um entregável diferente:

| Skill | Uso |
|---|---|
| `storytelling-apresentacao` | Estruturar e revisar a narrativa de apresentações, relatórios e comunicações executivas: contexto, Grande Ideia, storyboard, arco narrativo, lógica horizontal/vertical, repetição. |
| `storytelling-grafico` | Escolher o tipo certo de gráfico, eliminar saturação visual (Princípios de Gestalt), usar atributos pré-atentivos (cor, tamanho, posição) para dirigir atenção, e evitar armadilhas comuns (pizza, 3D, gráfico espaguete). |
| `storytelling-dashboard` | Compor painéis multi-visual de consumo recorrente: hierarquia de KPIs, densidade por cadência de consumo, sistema de cor consistente, layout e erros recorrentes. |

As três skills se complementam: uma apresentação (`storytelling-apresentacao`)
normalmente contém gráficos (`storytelling-grafico`); um dashboard
(`storytelling-dashboard`) é composto de vários gráficos individuais também guiados
por `storytelling-grafico`.

## Setup

Nenhuma configuração, credencial ou integração externa é necessária. O plugin não
inclui MCP servers, agents nem hooks — apenas conhecimento de domínio carregado sob
demanda.

## Uso

As skills são acionadas automaticamente pelo Claude quando a conversa envolve criar,
estruturar ou revisar apresentações, gráficos ou dashboards. Também podem ser
mencionadas diretamente: "use a skill storytelling-grafico para revisar este gráfico".

Cada skill mantém um `SKILL.md` enxuto com o processo principal e arquivos em
`references/` com aprofundamento técnico (catálogo de gráficos, princípios de Gestalt,
arco narrativo, densidade de dashboards), carregados sob demanda.

## Fonte

Todo o conteúdo é derivado dos capítulos 1 a 9 de *Storytelling com Dados: Um guia
sobre visualização* (Cole Nussbaumer Knaflic; edição brasileira Alta Books, 2019;
original *Storytelling With Data*, Wiley, 2015), adaptado para aplicação genérica via
skills acionáveis por Claude.
