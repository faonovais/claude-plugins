---
name: storytelling-apresentacao
description: >
  This skill should be used when the user asks to "criar uma apresentação com dados",
  "estruturar slides", "montar um roteiro de apresentação", "contar uma história com
  meus dados", "preparar uma reunião de resultados", "definir a Grande Ideia da
  apresentação", "fazer o storyboard de uma comunicação", ou pedir revisão/crítica de
  uma apresentação ou relatório já existente sob a ótica de storytelling. Aplica-se a
  qualquer domínio de negócio (não é específico de nenhuma indústria ou ferramenta).
metadata:
  version: "0.1.0"
  author: "Fábio Novais"
  based_on: "Storytelling com Dados — Cole Nussbaumer Knaflic (Alta Books, 2019)"
---

# Storytelling em Apresentações de Dados

Aplicar os princípios do livro *Storytelling com Dados* (Cole Nussbaumer Knaflic) para
estruturar e revisar apresentações, relatórios executivos e comunicações que usam
dados para embasar uma decisão. Os princípios são genéricos: aplicam-se a qualquer
setor, ferramenta (PowerPoint, Google Slides, PDF, e-mail, Power BI em modo
apresentação) e tipo de público.

Não tratar isto como um guia de estética de slides. É um processo de estruturação de
argumento antes de qualquer ferramenta de apresentação ser aberta.

## Quando usar esta skill vs. as outras do plugin

- Use `storytelling-apresentacao` para estruturar a narrativa, o argumento e a
  sequência de uma comunicação (reunião, relatório, e-mail, deck).
- Use `storytelling-grafico` quando a pergunta for sobre qual gráfico escolher ou como
  simplificar um gráfico específico.
- Use `storytelling-dashboard` quando o entregável for um painel multi-visual de
  consumo recorrente (não uma narrativa linear com início e fim).
- Nada impede combinar as três: uma apresentação normalmente contém gráficos
  (`storytelling-grafico`) organizados por uma narrativa (`storytelling-apresentacao`).

## Processo (seguir nesta ordem, sem pular etapas)

### 1. Entender o contexto antes de qualquer conteúdo

Antes de sugerir estrutura, slide ou gráfico, obter (perguntando ao usuário se não
estiver claro):

- **Quem é o público?** Nível de familiaridade com os dados, poder de decisão, viés ou
  preocupações conhecidas.
- **O que o público precisa saber ou fazer** como resultado desta comunicação? Se a
  resposta for vaga ("informar sobre o desempenho"), insistir até obter uma ação ou
  decisão concreta.
- **Mecanismo de comunicação**: apresentação ao vivo, documento para leitura
  autônoma, e-mail, dashboard estático anexado. Isso muda radicalmente o nível de
  detalhe e de anotação necessário (um documento lido sozinho precisa de mais texto de
  apoio do que um slide narrado ao vivo).
- **Tom desejado**: formal/executivo, técnico, urgente, etc.

Distinguir explicitamente **análise exploratória** (testar hipóteses, vasculhar os
dados) de **análise explanatória** (comunicar uma conclusão já encontrada). Esta skill
serve para a fase explanatória. Se o usuário ainda está explorando os dados e não sabe
o que quer dizer, não force uma narrativa prematura — primeiro ajude a decidir qual é
a mensagem.

### 2. Reduzir a mensagem à Grande Ideia

Aplicar o conceito de Nancy Duarte (citado no livro): a Grande Ideia deve, em uma
única frase:

1. Articular um ponto de vista específico (não um tema genérico como "vendas do
   trimestre" — e sim "as vendas do trimestre caíram por causa de X e recomendamos Y");
2. Transmitir o que está em jogo (por que o público deveria se importar);
3. Ser uma frase completa, não um título.

Se o usuário não tiver essa frase pronta, ajudar a formulá-la fazendo perguntas até
chegar em uma sentença única e acionável. Rejeitar Grandes Ideias que sejam apenas
descrição de tema ("Análise de safra 2025/26") — exigir ponto de vista e recomendação.

Testar também a "história de 3 minutos": se o usuário tivesse apenas 3 minutos com o
público, o que diria? Essa versão condensada ajuda a identificar o que é essencial
versus o que é apoio.

### 3. Montar o storyboard antes de abrir qualquer ferramenta

Recomendar explicitamente **não começar pela ferramenta de apresentação**. Propor a
estrutura em texto simples ou lista sequencial primeiro (o equivalente a notas
adesivas): cada "cartão" do storyboard é uma ideia, um dado ou uma transição — não um
slide finalizado. Isso evita apego prematuro a conteúdo que precisará ser cortado.

Estruturar o storyboard como uma história com começo, meio e fim (estrutura de três
atos):

- **Começo**: contexto, situação atual, por que isso importa agora. Estabelece o
  "normal" contra o qual a tensão será comparada.
- **Meio**: a tensão/complicação — o que mudou, o problema, a oportunidade, os dados
  que sustentam isso. É onde a maior parte da evidência analítica entra.
- **Fim**: a resolução — a recomendação, a decisão pedida, os próximos passos. A
  Grande Ideia deve aparecer aqui, claramente destacada, não diluída entre outros
  pontos.

### 4. Escolher a lógica de fluxo

Oferecer ao usuário (ou escolher com justificativa) uma das estratégias do livro:

- **Lógica horizontal**: cada slide/seção deve fazer sentido lendo-se apenas os
  títulos em sequência, como um resumo executivo embutido na estrutura. Útil para
  quando o público pode não prestar atenção total ou for ler depois por cima.
- **Lógica vertical**: cada slide individual deve ser autossuficiente e fazer sentido
  sozinho, sem depender dos slides vizinhos. Útil para documentos que circulam
  isoladamente (encaminhados por e-mail, lidos fora de ordem).
- **Storyboard inverso**: pegar uma comunicação já pronta e mapear o fluxo real
  resultante, para checar se a lógica pretendida realmente se sustenta. Usar esta
  técnica ao revisar apresentações já existentes.

### 5. Usar repetição de forma estratégica

Aplicar a técnica "diga o que vai dizer, diga, diga o que disse": recapitular a Grande
Ideia na abertura, reforçá-la ao longo do argumento e repeti-la no fechamento. Isso não
é redundância desnecessária — é a técnica que ajuda a mensagem central a ser lembrada.
Não confundir com repetir dados ou gráficos sem propósito.

### 6. Adaptar para o formato de entrega

- **Apresentação falada ao vivo**: slides podem ter menos texto de apoio, pois o
  apresentador complementa verbalmente. Priorizar poucos pontos por slide.
- **Documento de leitura autônoma** (relatório, PDF, e-mail): precisa de mais contexto
  escrito, títulos mais descritivos (ver `storytelling-grafico` para títulos de
  gráficos como frase-conclusão) e notas explicativas, já que não haverá narrador.

## Checklist de revisão (usar ao avaliar uma apresentação já existente)

Percorrer e responder objetivamente para cada item, apontando riscos concretos, não
opiniões estéticas genéricas:

1. A Grande Ideia é identificável em uma única frase? Está destacada no fechamento (ou
   na abertura, se o público exigir a conclusão logo de início)?
2. Existe começo, meio e fim reconhecíveis, ou o conteúdo é uma sequência de slides sem
   arco?
3. Ao ler apenas os títulos em sequência (lógica horizontal), a história ainda faz
   sentido?
4. Há slides que só fazem sentido com narração ao vivo, mas que serão distribuídos
   como documento autônomo (ou vice-versa)?
5. Cada seção sustenta a Grande Ideia, ou há conteúdo interessante mas irrelevante
   para a decisão pedida (saturação narrativa — ver `storytelling-grafico` para
   saturação visual)?
6. O pedido de ação/decisão está explícito e inequívoco no fechamento?

## Referências

- `references/grande-ideia-e-storyboard.md`: roteiro detalhado de perguntas para
  extrair contexto, Grande Ideia e montar o storyboard com o usuário.
- `references/arco-narrativo.md`: aprofundamento sobre estrutura de três atos, lógica
  horizontal/vertical, storyboard inverso e poder da repetição, com exemplos genéricos
  aplicáveis a qualquer setor.
