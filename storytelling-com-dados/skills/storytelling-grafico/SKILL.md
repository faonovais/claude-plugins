---
name: storytelling-grafico
description: >
  This skill should be used when the user asks "que tipo de gráfico devo usar",
  "como escolher a visualização certa", "revisar este gráfico", "simplificar um
  gráfico", "por que não usar gráfico de pizza", "remover saturação de um gráfico",
  "dar mais destaque a um dado no gráfico", "esse gráfico está confuso", or requests
  help designing, choosing, or critiquing any chart, graph, or visual (bar chart, line
  chart, table, heatmap, etc.), regardless of the tool used (Power BI, Excel, Python,
  Tableau, etc.) or industry. Aplica-se a qualquer domínio de negócio.
metadata:
  version: "0.1.0"
  author: "Fábio Novais"
  based_on: "Storytelling com Dados — Cole Nussbaumer Knaflic (Alta Books, 2019)"
---

# Storytelling em Gráficos e Visualizações

Aplicar os princípios dos capítulos 2, 3, 4, 6 e 9 do livro *Storytelling com Dados*
para escolher o tipo de visual correto, eliminar saturação e dirigir a atenção do
público para o que importa. Estes princípios são independentes de ferramenta (Power
BI, Excel, Python/matplotlib, Tableau, etc.) e de setor.

## Quando usar esta skill vs. as outras do plugin

- Use esta skill para decisões sobre **um gráfico ou tabela específico**: tipo de
  visual, remoção de saturação, hierarquia de destaque, título e anotações.
- Use `storytelling-apresentacao` quando a pergunta for sobre a narrativa que conecta
  vários gráficos em uma comunicação com início, meio e fim.
- Use `storytelling-dashboard` quando o objetivo for o layout de um painel com
  múltiplos visuais de consumo recorrente (não uma sequência narrativa linear).

## Processo

### 1. Entender o que o gráfico precisa fazer (forma segue função)

Antes de sugerir um tipo de gráfico, perguntar ou inferir: o que o público precisa
**fazer** com esse dado? Comparar categorias? Ver uma tendência no tempo? Ver a
composição de um total? Ver a relação entre duas variáveis? A resposta determina o
tipo de gráfico — nunca escolher um tipo por preferência estética antes de saber a
função.

### 2. Escolher o tipo de visual (catálogo do capítulo 2)

Consultar `references/catalogo-de-graficos.md` para a lista completa de casos de uso.
Resumo de decisão rápida:

| Objetivo | Visual recomendado |
|---|---|
| Um único valor-chave, sem necessidade de comparação | Texto simples (um número grande) |
| Comparar valores exatos e permitir leitura precisa | Tabela |
| Visão geral de padrão em muitas linhas/colunas de números | Mapa de calor |
| Tendência de uma métrica ao longo do tempo (série contínua) | Gráfico de linhas |
| Mudança entre dois pontos no tempo, várias categorias | Gráfico de inclinação (slopegraph) |
| Comparar categorias em um ponto no tempo | Gráfico de barras verticais |
| Comparar categorias e mostrar composição simultaneamente | Barras verticais empilhadas (com cautela — ver ressalvas) |
| Mostrar como um valor inicial se decompõe até um valor final | Gráfico de cascata (waterfall) |
| Comparar muitas categorias (rótulos longos) | Gráfico de barras horizontais |
| Comparar muitas categorias com composição | Barras horizontais empilhadas (com cautela) |
| Comparar duas magnitudes de forma aproximada, com pouco espaço | Área quadrada |

**Nunca recomendar** gráfico de pizza, gráfico de rosca (donut) ou qualquer gráfico
3D, pelos motivos explicados no livro: pizza e rosca dependem de comparação de área e
ângulo, que o olho humano interpreta mal; 3D distorce a percepção de magnitude por
perspectiva. Se o usuário insistir nesses tipos, explicar o motivo técnico da recusa e
oferecer a alternativa (barras ordenadas, geralmente) — ver
`references/catalogo-de-graficos.md` para o argumento completo e alternativas por
caso.

Gráficos empilhados (barras ou área): usar com cautela. Apenas a categoria da base
(que começa em zero) é comparável com precisão; as demais "flutuam" e são difíceis de
comparar entre si. Preferir alternativa (pequenos múltiplos, gráfico de linhas, ou
barras não empilhadas lado a lado) quando a comparação entre categorias intermediárias
for importante.

Evitar ativamente o **gráfico espaguete**: múltiplas linhas sobrepostas e coloridas
sem hierarquia, ilegível. Ver `references/saturacao-e-atencao.md` para estratégias de
resolução (destacar 1-2 linhas relevantes e apagar/acinzentar as demais, usar pequenos
múltiplos, ou rotular diretamente as linhas em vez de usar legenda).

### 3. Eliminar saturação (capítulo 3 — a saturação é inimiga)

Cada elemento visual consome carga cognitiva do público. Antes de adicionar qualquer
elemento (grade, borda, sombra, marcador, cor decorativa), perguntar se ele carrega
informação. Se não, remover.

Aplicar os seis Princípios da Gestalt de Percepção Visual (detalhados em
`references/saturacao-e-atencao.md`):

1. **Proximidade** — elementos próximos são percebidos como grupo. Usar para
   posicionar legendas coladas aos dados em vez de longe, em caixa separada.
2. **Similaridade** — elementos com mesma cor/forma/tamanho são percebidos como
   relacionados. Usar cor consistente para a mesma categoria em todos os visuais de uma
   mesma comunicação.
3. **Fechamento (enclausuramento)** — o cérebro completa formas incompletas. Usar para
   remover bordas e caixas desnecessárias: o alinhamento e o espaço em branco já
   sugerem o agrupamento, sem precisar de contorno.
4. **Continuidade** — o olho segue linhas contínuas. Remover linhas de grade,
   eixos e bordas de gráfico que não carregam informação adicional além do que os
   próprios dados já comunicam.
5. **Conexão** — elementos conectados por uma linha são percebidos como relacionados
   mais fortemente que por cor/proximidade. Usar em gráficos de inclinação e em
   anotações que ligam texto a um ponto de dado.
6. Consequência prática combinada: alinhamento consistente, uso estratégico de espaço
   em branco (não é espaço desperdiçado — é uma ferramenta de agrupamento) e contraste
   deliberado (não decorativo) entre elementos de destaque e elementos de contexto.

Checklist prático de remoção (aplicar nesta ordem):

1. Remover bordas/molduras de gráfico e de tabela.
2. Remover linhas de grade ou reduzi-las ao mínimo necessário para leitura.
3. Remover eixos redundantes com rótulos de dado já visíveis.
4. Remover cores decorativas sem significado categórico.
5. Remover legendas quando for possível rotular diretamente os elementos.
6. Simplificar rótulos numéricos (menos casas decimais, arredondamento apropriado ao
   contexto de decisão).

### 4. Dirigir a atenção com atributos pré-atentivos (capítulo 4)

Atributos pré-atentivos (tamanho, cor, posição na página, negrito) são processados
pelo cérebro antes da atenção consciente — por isso são a ferramenta mais eficaz para
criar hierarquia visual.

- Usar **cor com intenção estratégica, não decorativa**: reservar uma cor de destaque
  (ex.: um tom saturado) para o(s) ponto(s) que sustentam a Grande Ideia, e usar
  cinza/tons neutros para o restante dos dados de contexto. Nunca usar paleta "arco-íris"
  para categorias sem hierarquia de importância — isso distribui atenção igualmente e
  não comunica nada.
- Usar **tamanho e posição** para reforçar hierarquia: o que é mais importante deve
  ocupar mais espaço visual ou posição de leitura primária (topo/esquerda em contextos
  ocidentais).
- Considerar **acessibilidade**: evitar combinações de cor problemáticas para
  daltonismo (ex.: vermelho/verde puro como único diferenciador) e verificar se o
  contraste também funciona em impressão preto-e-branco/escala de cinza, quando
  aplicável.
- Construir a hierarquia visual em camadas: 1) o que quero que vejam primeiro, 2) o
  que dá suporte, 3) o que é apenas contexto disponível para quem quiser aprofundar.

### 5. Títulos, legendas e anotações (capítulo 6)

- Título do gráfico deve ser uma **frase-conclusão**, não uma descrição do eixo (evitar
  "Vendas por mês"; preferir "Vendas cresceram 15% após a mudança de preço em março").
  Exceção: relatórios de referência/exploração onde não há uma conclusão única a
  destacar — nesse caso, título descritivo é aceitável.
- Anotações diretamente no gráfico (texto próximo ao ponto relevante) comunicam mais
  rápido que legendas separadas ou parágrafos de texto ao lado.
- Ordenar os dados de forma que sustente o argumento (ex.: ordenar categorias por
  valor, não alfabeticamente, salvo quando a ordem alfabética/cronológica for
  relevante para o argumento).

## Checklist de revisão rápida (para gráfico já existente)

1. O tipo de gráfico corresponde à função pretendida (comparação, tendência,
   composição, relação)? Não é pizza/rosca/3D?
2. Existe algum elemento sem função informativa (borda, grade, sombra, cor decorativa)?
3. A cor está sendo usada estrategicamente para destacar 1-2 pontos-chave, ou está
   distribuída sem hierarquia?
4. O título comunica a conclusão, ou apenas descreve os eixos?
5. Em caso de múltiplas linhas/categorias, há risco de gráfico espaguete? Como reduzir?
6. Os rótulos e a ordenação dos dados sustentam o argumento pretendido?

## Referências

- `references/catalogo-de-graficos.md`: catálogo completo dos tipos de visual do
  capítulo 2, casos de uso, e o argumento técnico contra pizza/rosca/3D.
- `references/saturacao-e-atencao.md`: aprofundamento nos seis Princípios de Gestalt,
  uso estratégico de cor e estratégias específicas contra o gráfico espaguete (capítulo
  9).
