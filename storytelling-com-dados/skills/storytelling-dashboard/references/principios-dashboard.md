# Densidade de informação, layout e erros recorrentes em dashboards

Aprofundamento de apoio à SKILL.md. Os princípios do livro *Storytelling com Dados*
foram escritos majoritariamente para peças lineares; este documento traduz esses
princípios para o contexto de dashboard, que é multi-visual e sem sequência de leitura
garantida.

## Densidade de informação por cadência de consumo

| Cadência | Objetivo do usuário | Densidade recomendada | Padrão de layout |
|---|---|---|---|
| Monitoramento contínuo (várias vezes ao dia) | Detectar desvio em segundos | Mínima — poucos KPIs, cor binária (dentro/fora do esperado) | Tela única, sem scroll, sem filtros visíveis por padrão |
| Revisão periódica (diária/semanal) | Entender causa de variação | Média — KPIs + 2-4 gráficos de diagnóstico | Tela única com possível scroll curto; filtros de período visíveis |
| Exploração/análise (sob demanda) | Investigar a fundo, testar hipóteses | Alta — tabelas, drill-down, múltiplos filtros | Múltiplas páginas/abas; navegação explícita entre visão geral e detalhe |

Erro recorrente a sinalizar: usar densidade de exploração em um dashboard de
monitoramento (sobrecarrega o usuário que só quer saber "está tudo bem?"), ou o
inverso — um dashboard de exploração raso demais para sustentar investigação real.

## Padrões de layout recomendados

- **Regra do F/Z**: em culturas de leitura ocidental, o olhar tende a percorrer a tela
  em um padrão F ou Z (esquerda para direita, cima para baixo, com atenção decrescente
  conforme desce). Posicionar os KPIs de camada 1 (ver SKILL.md) no canto superior
  esquerdo ou ao longo do topo.
- **Grade consistente**: definir uma grade de colunas/linhas fixa para todos os
  visuais do painel, evitando tamanhos arbitrários. Ferramentas de BI corporativas
  (Power BI, Tableau, Looker) geralmente oferecem grade nativa — usá-la em vez de
  posicionamento livre.
- **Cabeçalho fixo de contexto**: nome do painel, período de referência e
  data/hora da última atualização devem estar sempre visíveis — ausência disso é uma
  falha de auditabilidade e de confiança do usuário no dado.
- **Filtros/seletores**: agrupar em uma barra consistente (topo ou lateral), nunca
  espalhados entre os visuais. Cada filtro deve ter escopo claro (afeta o painel
  inteiro ou apenas uma seção) — ambiguidade de escopo é uma fonte comum de erro de
  leitura pelo usuário final.

## Erros recorrentes em dashboards corporativos (para checklist de revisão)

1. **Todos os visuais do mesmo tamanho e mesma cor de destaque** — nenhuma hierarquia,
   o usuário não sabe por onde começar.
2. **Paleta "arco-íris" sem significado categórico** — cores diferentes por gráfico,
   sem sistema de cor coerente entre visuais do mesmo painel.
3. **Excesso de gráficos de pizza/rosca em cartões pequenos** — o problema de
   comparação de ângulo/área piora ainda mais em espaço reduzido.
4. **Bordas e sombras em cada cartão** — saturação visual desnecessária; espaço em
   branco e alinhamento consistente substituem a necessidade de contorno.
5. **KPI sem meta ou referência de comparação** — um número sozinho, sem contexto
   (meta, período anterior, benchmark), não permite ao usuário concluir se é bom ou
   ruim; isso viola o princípio de contexto do capítulo 1 aplicado ao dashboard.
6. **Falta de rastreabilidade da fonte/atualização** — ausência de data de última
   atualização ou origem do dado, o que compromete a confiança e a auditabilidade do
   painel, especialmente em ambientes corporativos com múltiplas fontes.
7. **Filtros que alteram silenciosamente o significado de um KPI** — ex.: um filtro de
   período que muda a base de cálculo de um indicador sem deixar isso explícito na
   tela, gerando interpretação incorreta.
8. **Densidade uniforme independentemente do público** — o mesmo dashboard servido sem
   adaptação tanto para quem precisa de monitoramento rápido quanto para quem precisa
   de exploração detalhada, forçando um dos dois públicos a um formato inadequado.

## Relação com modelo semântico e governança (aplicável a BI corporativo)

Quando o dashboard consome um modelo semântico centralizado com medidas padronizadas,
a consistência de storytelling (cor, hierarquia, nomenclatura de KPI) deve ser tratada
como parte da governança do modelo, não decidida ad hoc em cada relatório/página. Um
mesmo KPI não deveria ter definição, cor ou nomenclatura diferente em painéis
diferentes da mesma organização — isso é tanto um problema de storytelling quanto de
governança de dados.
