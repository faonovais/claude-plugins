# Catálogo de tipos de visual (capítulo 2 do livro)

Referência detalhada para consulta ao decidir o tipo de visual. Todos os tipos abaixo
são genéricos e aplicáveis a qualquer domínio — os exemplos usam termos de negócio
neutros, adaptar a terminologia do usuário quando necessário.

## Texto simples

**Quando usar**: um único número ou poucos números-chave que resumem toda a mensagem,
sem necessidade de comparação visual. Ex.: "Faturamento do trimestre: R$ 4,2 milhões
(+8% vs. trimestre anterior)."

**Cuidado**: usar fonte grande e destaque para o número; complementar com uma frase de
contexto (o "+8%" acima não significa nada sozinho sem a comparação).

## Tabela

**Quando usar**: quando o público precisa ler valores exatos, comparar múltiplas
métricas por múltiplas categorias simultaneamente, ou consultar dados específicos
(não uma visão geral de padrão). Boa para públicos heterogêneos que vão procurar
números diferentes.

**Cuidado**: tabelas não comunicam padrão visualmente — se o objetivo é mostrar
tendência ou comparação de magnitude, preferir gráfico. Usar formatação condicional
sutil (não saturada) se quiser guiar o olhar sem virar mapa de calor completo.

## Mapa de calor

**Quando usar**: visão geral de padrão em uma matriz grande de números (muitas linhas
x colunas) onde o valor exato de cada célula é secundário à percepção do padrão geral
(picos, vales, agrupamentos).

**Cuidado**: escolher uma escala de cor sequencial (não arco-íris) e sempre incluir
legenda de escala. Evitar quando o público precisa de valores exatos — nesse caso,
combinar com tabela ou permitir drill-down.

## Gráfico de linhas

**Quando usar**: tendência de uma métrica contínua ao longo do tempo. É o tipo padrão
para séries temporais.

**Cuidado**: limitar o número de linhas simultâneas (ver "gráfico espaguete" em
`saturacao-e-atencao.md`). Eixo X deve ser proporcional ao tempo real (não distorcer
intervalos).

## Gráfico de inclinação (slopegraph)

**Quando usar**: comparar a mudança de várias categorias entre exatamente dois pontos
no tempo (ex.: "antes" e "depois"). Cada categoria vira uma linha entre dois pontos,
permitindo ver quem subiu, quem caiu e a magnitude relativa da mudança.

**Cuidado**: funciona bem até ~8-10 categorias; acima disso, considerar destacar
apenas as categorias relevantes e acinzentar as demais.

## Gráfico de barras verticais

**Quando usar**: comparar valores entre categorias discretas em um único ponto no
tempo. É o gráfico de comparação mais legível e deve ser a escolha padrão quando não
houver razão específica para outro tipo.

**Cuidado**: eixo Y deve começar em zero (barras codificam magnitude pelo comprimento
— cortar o eixo distorce a percepção de diferença entre categorias). Ordenar por
valor quando a ordem não for intrinsecamente temporal ou categórica fixa.

## Gráfico de barras verticais empilhadas

**Quando usar**: mostrar tanto o total quanto a composição de cada categoria,
quando a comparação da categoria da base (a mais próxima do eixo zero) for o
principal interesse.

**Cuidado**: apenas a série da base é comparável com precisão entre barras; as séries
"flutuantes" no meio da pilha são difíceis de comparar. Se a comparação entre séries
intermediárias for importante, preferir pequenos múltiplos ou barras lado a lado (não
empilhadas).

## Gráfico de cascata (waterfall)

**Quando usar**: mostrar como um valor inicial se decompõe, através de incrementos e
decrementos sucessivos, até um valor final (ex.: reconciliação de orçamento, ponte de
margem, evolução de estoque).

**Cuidado**: rotular claramente os incrementos positivos e negativos com cores
distintas e consistentes; incluir os totais inicial e final destacados.

## Gráfico de barras horizontais

**Quando usar**: mesma lógica das barras verticais, mas quando os rótulos das
categorias são longos (nomes, descrições) e não caberiam legivelmente no eixo X de um
gráfico vertical.

**Cuidado**: mesma regra de eixo começando em zero e ordenação por valor.

## Gráfico de barras horizontais empilhadas

**Quando usar**: composição por categoria com rótulos longos. Útil para visualizar,
por exemplo, distribuição percentual (100% empilhado) entre segmentos.

**Cuidado**: mesmas ressalvas das barras verticais empilhadas quanto à comparabilidade
das séries do meio.

## Gráfico de área quadrada (square area)

**Quando usar**: comparação aproximada de duas ou poucas magnitudes muito distintas em
espaço reduzido, quando precisão de leitura não é crítica.

**Cuidado**: usado com moderação — comparação de área é cognitivamente mais difícil que
comparação de comprimento (barras). Preferir barras sempre que o espaço permitir.

## Visuais a evitar e por quê

### Gráfico de pizza e gráfico de rosca (donut)

Motivo técnico: o olho humano é ruim em comparar ângulos e áreas com precisão — muito
pior do que em comparar comprimentos (como em um gráfico de barras). Isso é
especialmente problemático com mais de 2-3 fatias, ou quando as fatias têm tamanhos
próximos entre si.

Alternativa recomendada: gráfico de barras (ordenado por valor) para comparar as
partes; se o ponto for mostrar a relação parte/todo de uma única categoria contra o
total, considerar um indicador de texto simples ("categoria X representa 62% do
total") complementado por uma barra.

### Gráficos 3D

Motivo técnico: a perspectiva 3D distorce a percepção de profundidade e magnitude —
elementos mais "próximos" na perspectiva parecem maiores mesmo tendo o mesmo valor que
elementos mais distantes. Não há ganho informacional, apenas ruído visual.

Alternativa recomendada: a versão 2D equivalente do mesmo gráfico (barra, linha, etc.).
Não existe caso de uso legítimo para 3D em visualização de dados de negócio.
