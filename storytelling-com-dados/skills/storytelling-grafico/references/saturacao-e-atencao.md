# Saturação, Gestalt e atenção pré-atentiva (capítulos 3, 4 e 9 do livro)

## Os seis Princípios da Gestalt de Percepção Visual

Origem: Escola de Psicologia Gestalt. O livro aplica seis desses princípios à
visualização de dados. Usar esta lista para justificar tecnicamente decisões de
design ao usuário, em vez de alegar preferência estética.

1. **Proximidade**: elementos próximos entre si são percebidos como um grupo, mesmo
   sem qualquer linha ou caixa os conectando. Aplicação prática: posicionar rótulos e
   legendas diretamente ao lado do dado a que se referem, não em uma legenda distante;
   agrupar visuais relacionados fisicamente próximos em um dashboard.

2. **Similaridade**: elementos com a mesma cor, forma ou tamanho são percebidos como
   pertencentes à mesma categoria. Aplicação prática: manter a mesma cor para a mesma
   categoria/série em todos os gráficos de uma mesma comunicação; não reutilizar uma
   cor para significados diferentes.

3. **Fechamento (enclausuramento)**: o cérebro completa automaticamente formas
   parcialmente delimitadas por espaço em branco ou alinhamento, sem precisar de
   contorno explícito. Aplicação prática: remover bordas e caixas ao redor de gráficos
   e tabelas — o alinhamento e o espaçamento já comunicam o agrupamento.

4. **Continuidade**: o olho tende a seguir linhas e a perceber elementos alinhados
   como uma sequência contínua. Aplicação prática: remover linhas de grade e eixos
   redundantes; o padrão dos próprios pontos de dado já fornece a continuidade visual
   necessária.

5. **Conexão**: elementos ligados por uma linha física são percebidos como mais
   fortemente relacionados do que elementos apenas próximos ou similares.
   Aplicação prática: usar linhas de conexão em gráficos de inclinação; usar uma linha
   fina para ligar uma anotação de texto ao ponto de dado específico a que se refere.

6. **Região comum**: (mencionado em conjunto com fechamento) elementos dentro de uma
   mesma área delimitada por espaço em branco são percebidos como grupo. Substitui a
   necessidade de caixas com borda — um espaçamento maior entre grupos já basta.

## Alinhamento, espaço em branco e contraste

- **Alinhamento**: todo elemento na página/tela deve estar alinhado a algum eixo
  (esquerda, centro, borda de outro elemento). Alinhamento inconsistente é uma das
  formas mais comuns e mais fáceis de corrigir de saturação visual.
- **Espaço em branco**: não é espaço desperdiçado — é a ferramenta mais barata de
  agrupamento e hierarquia (ver princípio de fechamento/região comum acima). Resistir
  ao impulso de preencher todo o espaço disponível com mais elementos.
- **Contraste**: deve ser usado deliberadamente para criar hierarquia (o elemento de
  destaque contrasta com o restante), nunca de forma decorativa. Se tudo tem
  contraste alto, nada se destaca.

## Atributos pré-atentivos (capítulo 4)

Atributos processados pelo cérebro em milissegundos, antes da atenção consciente:
tamanho, cor (matiz e saturação), posição na página, orientação, forma, espessura de
linha e negrito/itálico em texto.

Uso estratégico:

- Escolher **um** atributo pré-atentivo por vez para criar destaque (normalmente cor).
  Combinar múltiplos atributos de destaque na mesma peça de informação sobrecarrega e
  na verdade reduz a clareza.
- Reservar a cor de destaque (mais saturada/contrastante) exclusivamente para o(s)
  ponto(s) essenciais à Grande Ideia. Todo o resto do gráfico deve usar tons neutros
  (cinza) — isso cria hierarquia automática sem precisar de texto explicativo.
- Construir hierarquia visual em camadas conscientes: nível 1 (o que deve ser visto
  primeiro), nível 2 (suporte), nível 3 (contexto disponível, mas não destacado).
  Perguntar ao usuário, se não for óbvio, qual dado pertence a qual camada antes de
  aplicar cor.
- Cor categórica (uma cor por categoria, tipo "arco-íris") só se justifica quando
  todas as categorias têm importância igual e o público precisa distingui-las
  simultaneamente. Na maioria dos contextos de negócio isso não é o caso — há sempre
  uma categoria mais relevante à mensagem, que deveria ganhar destaque diferenciado.

## Estratégias contra o gráfico espaguete (capítulo 9)

Gráfico espaguete: múltiplas linhas de cores variadas sobrepostas em um gráfico de
linhas, sem hierarquia, tornando impossível seguir qualquer série individual.

Estratégias, em ordem de preferência:

1. **Destacar 1-2 linhas relevantes** com cor saturada e reduzir todas as demais a
   cinza claro fino, mantendo-as visíveis apenas como contexto de fundo.
2. **Pequenos múltiplos**: dividir em vários gráficos pequenos, um por categoria,
   organizados em grade, todos com a mesma escala de eixo para permitir comparação.
   Preferível quando todas as categorias importam, mas simultaneamente é ilegível.
3. **Rotulagem direta**: rotular cada linha com o nome da categoria diretamente ao
   lado do ponto final da linha, eliminando a necessidade de legenda separada (aplica
   o princípio de proximidade).
4. **Interatividade** (quando a ferramenta permitir, ex.: Power BI): permitir que o
   usuário final selecione/realce séries sob demanda, mantendo o padrão estático já
   simplificado (aplicar as estratégias 1-3 acima como estado padrão).

## Considerações de cor em fundo escuro (capítulo 9)

Quando o entregável usa tema escuro (dashboard, apresentação com fundo escuro):
saturação e brilho das cores precisam ser recalibrados — cores que funcionam bem em
fundo claro podem perder contraste ou "vibrar" desconfortavelmente em fundo escuro.
Testar a paleta especificamente no tema final antes de finalizar, não assumir que a
mesma paleta funciona nos dois contextos.
