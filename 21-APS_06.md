# APS 6 - Um Teste de Hipótese

## Introdução

Nós já sabemos calcular a probabilidade de a diferença entre as médias de dois grupos ser nula. Para isso, usamos o t-teste para duas amostras independentes. Neste exercício, vamos usar o t-teste em situações do mundo real.



## Enunciado da atividade

Nesta atividade, você vai observar um fenômeno em dois grupos amostrais diferentes. Após, vai aplicar um t-teste de amostras independentes para identificar se a média desses dois grupos é significativamente diferente.

Para isso, siga os seguintes passos:

1. Escolha um fenômeno à sua volta. O fenômeno deve ser mensurável. Por exemplo (esse já não vale): a altura das pessoas.
2. Escolha dois grupos em que seja possível amostrar o fenômento. Por exemplo: pessoas que jogam basquete e pessoas que não jogam basquete.
3. Colete dados sobre seu fenômeno, nas duas situações. Se não achar dados, ou julgar que não conseguirá coletá-los em tempo hábil, guarde essa ideia para depois, volte ao passo 1 e escolha outro fenômeno.
4. Usando um t-teste para duas amostras e com $\alpha=5\%$, verifique se a diferença entre as médias dos grupos é estatisticamente significativa.
5. Interprete o p-valor gerado pelo t-teste em relação à sua hipótese nula e contextualize esse resultado para o problema que você lidou.

## Sobre o uso de IA (ChatGPT, etc.)

ChatGPT e outros modelos de linguagem são ferramentas de produtividade importantes e relevantes. Por outro lado, seu uso indiscriminado pode se tornar um ruído no processo de produção e feedback das atividades, pelos seguintes motivos:

1. O texto produzido é um *proxy* para o entendimento do aluno. Analisando o texto, queremos entender quais são os *gaps* de aprendizado que acontecem, de forma que possamos planejar intervenções pertinentes.
2. O feedback fornecido parte do pressuposto de que o texto foi o melhor trabalho possível apresentado pelo aluno. Nesse contexto, o *feedback* tem a intenção de revisar e proporcionar ao aluno uma visão externa com o intuito de melhorar ou refinar sua compreensão e sua expressão sobre o tema. Fornecer *feedback* para um texto gerado por máquina não tem esse efeito, porém é tão ou mais trabalhoso que dar *feedback* para textos feitos por humanos.

Pensando nisso, vamos adotar as seguintes regras para o uso de ChatGPT e IAs generativas de forma geral para a redação de textos:

1. Caso o grupo decida usar ChatGPT ou equivalente para qualquer parte de sua redação, deve **obrigatoriamente** adicionar uma nova seção anexa ao relatório em que mostra todos os prompts e respostas do ChatGPT (ou todas as interações equivalentes).
2. Também, para cada trecho que use IA, o grupo deverá **explicitamente** justificar porque o trecho foi considerado correto. Justificativas vagas como "achamos pertinente", "condiz com a matéria", etc., não serão aceitas. Justificativas válidas são aquelas que associam explicitamente o texto fornecido pela IA a uma equação, observação ou raciocínio pertinentes ao texto.
3. Neste anexo citado e nas justificativas, não é permitido usar nenhum tipo de IA.
4. O uso de IA sem a citação adequada ou sem o anexo (qualquer um deles, ou ambos simultaneamente), se detectado, será considerado como cópia sem citação de fonte, e, portanto, violação do código de ética.

# Entregas esperadas

Você deve entregar, via Blackboard, um arquivo PDF (uma entrega por grupo!) contendo:

1. Nome do grupo
2. Título do trabalho, que deve ser algo como "Fenômeno X (seu fenômeno escolhido) nas situações A e B usando modelo (seu modelo)" (parafraseie isso!)
3. Um texto explicando todos os ítens do desenvolvimento com detalhe suficiente para permitir que alguém de outra turma desta disciplina possa reproduzir o mesmo experimento e criticá-lo. O texto deve deixar explícito:
   1. A hipótese nula
   2. A hipótese alternativa
   3. Os dados que foram usados, incluindo link para a base de dados (se houver) ou uma referência de como podemos obte-los,
   4. O procedimento para calcular o p-valor
   5. O nível de significância utilizado
   6. A decisão tomada com base no p-valor e sua relação com o problema.
4. Uma auto-avaliação do texto, justificando a nota que foi auto-atribuída com base na rubrica e em elementos do próprio texto.

# Rubricas e avaliação

Cada um dos ítens (exceto a auto-avaliação) será avaliado da seguinte forma:

| Rubrica | Descrição                                                                                                                                                                                                                                                                                                                                                            | Exemplo                                                                                                                                                              |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| F       | Não entregue, entregue fora do prazo, entregue fora do escopo ("fiz outra coisa")                                                                                                                                                                                                                                                                                     | Não entregar                                                                                                                                                        |
| E       | Entregue no prazo e dentro do escopo, mas a entrega tem um ou mais ítens ou sub-ítens faltando ou só é compreensível se for acompanhado deste enunciado (por exemplo, ao dizer "resposta ao ítem 2" ao invés de ter um título explicativo) ou está ilegível (exemplo: textos sem sentido ou figuras muito grandes / muito pequenas ou em resolução baixa)  | Colocar no título de uma figura: "ítem 1a"                                                                                                                         |
| D       | A entrega tem falhas graves de coesão ou coerência que impedem sua compreensão, ou faltam elementos essenciais (título, legenda, rótulos nos eixos), ou o texto deixa de indicar o que são ideias originais e o que são ideias retiradas de outras fontes, ou as ideias/dados são mostrados de forma embaralhada, sem guiar o leitor a um fluxo de pensamento. | Em um texto: "Existe impacto da renda na educação. Isso porque a renda pode estar ligada a condições de estudo. O estudo é essencial para formar seres humanos" |
| C       | A entrega não tem falhas graves. Todas as fontes de ideias são indicadas. A entrega traz ao menos um elemento errado ou ao menos um elemento supérfluo (que não contribui para a mensagem passada).                                                                                                                                                                | Em um texto: "Essa é uma fonte de 100W (Watts, unidade batizada em homenagem a James Watt, inventor da máquina a vapor")                                           |
| B       | A entrega tem todos os elementos necessários para passar a mensagem, a mensagem é clara, e não há elementos supérfluos.                                                                                                                                                                                                                                           | Título da figura: "Média de desempenho no ENEM 2022 por disciplina por faixa de renda", com rótulo no eixo Y: "Pontos" e rótulo no eixo X: "faixa de renda".     |
| A       | A entrega está correta e o conteúdo mostra ou induz uma análise crítica do contexto ou das implicações dos dados e informações coletadas.                                                                                                                                                                                                                      | Título da figura: "Desempenho no ENEM diminui com o aumento da renda", com rótulo no eixo Y: "Pontos" e rótulo no eixo X: "faixa de renda".                       |

A auto-avaliação será avaliada da seguinte forma:

| Rubrica | Descrição                                                                                                                                                                                  | Exemplo                                                                                                                                                                                                                                               |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| F       | Não entregue, entregue fora do prazo, entregue fora do escopo ("fiz outra coisa")                                                                                                           | Não entregar                                                                                                                                                                                                                                         |
| D       | Entregue no prazo e dentro do escopo, mas somente copia as rubricas que foram apresentadas, sem relacioná-las com o material apresentado, ou apresenta notas sem argumentar o motivo delas. | "Nota A, pois está correto e o conteúdo induz análise crítica do contexto"                                                                                                                                                                        |
| C       | Entregue, mas claramente puxa as notas "para cima" ou "para baixo" sem ter argumentos                                                                                                        | Entrega é uma figura sem título, mas auto-avaliação diz: "o título da figura está correto"                                                                                                                                                      |
| A       | Entregue, e argumentado corretamente                                                                                                                                                         | "Nota A porque a passagem `de acordo com Fulano et al.` mostra que os resultados obtidos condizem com a literatura", ou "Nota B, porque a figura tem todos os elementos, embora não tenha nenhuma indicação de uma leitura crítica do contexto. |

Para atingir cada nível, é necessário cumprir todos os requisitos do nível anterior. Cada uma das entregas será avaliada individualmente e isoladamente. A nota geral do trabalho será a **menor** entre as notas das entregas.

Caso haja interações com IAs, elas serão avaliadas de acordo com a seguinte rubrica:

| Rubrica           | Descrição                                                                                                                                                                                                                                                               |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Código de ética | Foi identificado o uso de Inteligência Artificial, mas o texto não demonstra clara e diretamente que uma ferramenta foi utilizada ou como ela foi utilizada.                                                                                                            |
| F                 | Somente colocou o enunciado da atividade como entrada da IA e fez alterações mínimas no resultado apresentado. Toda ou a maior parte da informação relevante do trabalho foi gerada pela IA.                                                                        |
| E                 | Trouxe tópicos específicos à IA, mas as conexões lógicas foram todas ou em sua maioria trazidas pela IA. OU: Uma ou mais informações inventadas pela IA (alucinações) foram transportadas para o texto sem crítica.                                             |
| D                 | O grupo trouxe alguns elementos relevantes para a IA, mas todas ou a maioria das conexões lógicas foram feitas pela própria IA.                                                                                                                                        |
| C                 | O grupo trouxe a maioria dos elementos relevantes para a IA, mas a IA ainda foi responsável por trazer ao menos um elemento essencial ao trabalho.                                                                                                                       |
| B                 | IA foi usada para frasear raciocínios, mas todos os elementos relevantes para a construção dos raciocínios foram fornecidas pelo grupo de trabalho.                                                                                                                   |
| A                 | IA foi usada apenas para correções estilísticas, e todo o conteúdo relevante e todas as linhas de raciocínio foram feitas pelo grupo de trabalho, OU a IA foi usada somente para obter ideias sobre o assunto e o grupo escreveu todo o conteúdo com suas palavras. |
