---
name: storytelling-dashboard
description: >
  This skill should be used when the user asks to "criar um dashboard", "montar um
  painel de indicadores", "organizar o layout de um dashboard", "revisar um dashboard
  existente", "definir KPIs de um painel executivo", "estruturar um dashboard no Power
  BI/Tableau/Looker", ou pedir orientação sobre a disposição de múltiplos
  gráficos/indicadores em uma única tela de consumo recorrente. Aplica-se a qualquer
  ferramenta de BI e qualquer domínio de negócio — não é específico de nenhuma
  indústria.
metadata:
  version: "0.1.0"
  author: "Fábio Novais"
  based_on: "Storytelling com Dados — Cole Nussbaumer Knaflic (Alta Books, 2019)"
---

# Storytelling em Dashboards

Adaptar os princípios do livro *Storytelling com Dados* — pensados originalmente para
peças lineares (slides, relatórios) — ao formato de dashboard: uma tela única,
multi-visual, de consumo recorrente e sem sequência de leitura garantida. Isso muda a
aplicação prática de alguns princípios (não há "começo, meio e fim" fixo como em uma
apresentação), mas os fundamentos de saturação, atenção pré-atentiva e função sobre
forma continuam valendo integralmente.

## Quando usar esta skill vs. as outras do plugin

- Use esta skill para **layout e composição de um painel** com múltiplos visuais
  consumido de forma recorrente (diário, semanal) sem apresentador guiando a leitura.
- Use `storytelling-grafico` para decidir o tipo de cada visual individual dentro do
  dashboard.
- Use `storytelling-apresentacao` se o entregável for, na verdade, um relatório
  narrativo linear ou uma apresentação ao vivo — mesmo que contenha capturas de
  dashboard.
- Um dashboard bem construído é o resultado de aplicar `storytelling-grafico` a cada
  visual individualmente e, depois, aplicar esta skill à composição do conjunto.

## Diferença estrutural em relação a uma apresentação

Um dashboard não tem sequência garantida de leitura: o usuário pode olhar em qualquer
ordem, voltar, ignorar seções. Por isso:

- Não existe "storyboard" linear como em `storytelling-apresentacao` — existe
  **hierarquia espacial**: o que precisa ser visto primeiro deve estar posicionado e
  destacado para isso, independentemente da ordem real de leitura do usuário.
- A "Grande Ideia" de um dashboard, quando existe, deve estar sempre visível (ex.: um
  KPI de destaque fixo no topo), não ao final como em uma narrativa.
- Repetição funciona diferente: em vez de repetir a mensagem ao longo do tempo de
  leitura, repetir a mesma métrica-chave em pontos de referência (ex.: o mesmo KPI
  visível tanto no resumo quanto no detalhe) para ancorar o usuário.

## Processo

### 1. Definir o propósito e a cadência de consumo

Perguntar (se não estiver claro):

- Quem consulta este dashboard e com que frequência (diário, ao final do ciclo,
  eventual)?
- É uma ferramenta de **monitoramento** (checar se algo está fora do esperado,
  consumida em segundos) ou de **exploração** (investigar detalhes, consumida em
  minutos)? Isso muda radicalmente a densidade de informação apropriada.
- Existe uma decisão ou ação recorrente que o dashboard deve viabilizar, ou é
  informativo por natureza (acompanhamento de indicadores sem ação direta associada)?

### 2. Definir hierarquia de KPIs antes do layout

Classificar cada métrica candidata em camadas, antes de desenhar qualquer visual:

1. **Camada 1 — KPIs de monitoramento**: os 2 a 5 números que respondem "está tudo
   bem ou não?" em poucos segundos. Devem ocupar a posição de maior destaque (tipicamente
   topo da tela, em contextos de leitura ocidental) e usar atributos pré-atentivos
   (tamanho, cor) para sinalizar status (ex.: dentro da meta / fora da meta).
2. **Camada 2 — Diagnóstico**: gráficos que explicam a variação dos KPIs de camada 1
   (tendência no tempo, decomposição por categoria, comparação).
3. **Camada 3 — Detalhe/drill-down**: tabelas ou visuais de suporte para quem precisa
   investigar a fundo. Pode ficar abaixo da dobra ou em página secundária.

Rejeitar dashboards que misturam as três camadas sem hierarquia visual — o sintoma
típico é "todos os visuais do mesmo tamanho, mesma cor de destaque", que é o
equivalente, em dashboard, ao gráfico sem atributos pré-atentivos aplicados.

### 3. Aplicar saturação e Gestalt à composição do painel

Os mesmos seis princípios de Gestalt (ver `storytelling-grafico/references/saturacao-e-atencao.md`)
se aplicam ao layout do dashboard como um todo, não só a cada gráfico individualmente:

- **Proximidade/região comum**: agrupar visuais relacionados fisicamente próximos;
  usar espaço em branco maior entre grupos temáticos diferentes em vez de bordas/caixas.
- **Similaridade**: manter a mesma paleta de cor para a mesma categoria/métrica em
  todos os visuais do painel — inconsistência de cor entre visuais do mesmo dashboard é
  um erro comum e caro em termos de confusão do usuário.
- **Alinhamento**: grade consistente entre os visuais (mesmas margens, mesmo
  espaçamento) — inconsistência de alinhamento é o defeito mais visível e mais barato
  de corrigir em um dashboard malfeito.

Evitar saturação específica de dashboard: filtros/seletores em excesso, múltiplas
legendas repetidas quando uma única legenda compartilhada bastaria, bordas em cada
cartão/visual (region comum via espaço em branco geralmente substitui a necessidade de
caixas com borda).

### 4. Cor como sistema, não por gráfico

Em um dashboard, a cor precisa funcionar como um sistema coerente entre todos os
visuais, não ser decidida gráfico a gráfico:

- Definir um significado fixo por cor antes de montar qualquer visual (ex.: uma cor
  única para "acima da meta", outra para "abaixo da meta", tons neutros para dados de
  contexto) e aplicar esse sistema em todos os visuais do painel.
- Evitar que a mesma cor tenha significados diferentes em visuais diferentes do mesmo
  painel — isso quebra o princípio de similaridade e gera interpretação incorreta.
- Se o dashboard tem tema escuro, validar a paleta especificamente nesse tema (ver
  considerações de cor em fundo escuro em `storytelling-grafico/references/saturacao-e-atencao.md`).

### 5. RLS, multi-tenant e modelo semântico (quando aplicável a BI corporativo)

Quando o dashboard for construído sobre um modelo semântico centralizado (ex.: Power
BI com RLS para múltiplos públicos/tenants), garantir que a hierarquia de KPIs e o
sistema de cor sejam consistentes entre todas as visões filtradas por RLS — o mesmo
usuário-tipo deve ver a mesma lógica de destaque independentemente do filtro de
tenant/unidade aplicado. Isso é uma questão de governança de storytelling, não apenas
de segurança de dado.

### 6. Testar com a pergunta do capítulo 1: quem e para quê

Reaplicar a pergunta central do livro no nível do dashboard inteiro: para cada
elemento do painel, perguntar se ele está lá porque algum público real precisa dele
para uma decisão ou monitoramento específico — ou porque "pode ser útil algum dia".
Elementos da segunda categoria são candidatos a corte ou a relegação para a camada de
detalhe/drill-down.

## Checklist de revisão (para dashboard já existente)

1. Existe hierarquia visual clara entre KPIs de monitoramento, diagnóstico e detalhe,
   ou todos os visuais competem pela mesma atenção?
2. A cor tem um significado consistente em todo o painel, ou muda de sentido entre
   visuais?
3. Há elementos sem função informativa (bordas, sombras, ícones decorativos, grades
   excessivas)?
4. O alinhamento e o espaçamento entre visuais seguem uma grade consistente?
5. Cada visual usa o tipo de gráfico correto para sua função (aplicar checklist de
   `storytelling-grafico`)?
6. Existe algum visual cuja utilidade real para o público-alvo não está clara — é
   candidato a corte?

## Referências

- `references/principios-dashboard.md`: aprofundamento sobre densidade de informação
  por cadência de consumo (monitoramento vs. exploração), padrões de layout e erros
  recorrentes em dashboards corporativos.
