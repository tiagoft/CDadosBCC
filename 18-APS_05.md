# APS 5 - Caracterizando modelos

## Introdução

Neste momento, você deve ser capaz de olhar ao seu redor e encontrar fenômenos que podem ser modelados por distribuições Binomial, Poisson ou Exponencial. Você também deve ser capaz de encontrar intervalos de confiança para a média de medidas usando o Teorema Central do Limite.

Nesta atividade, vamos usar dados reais e estimar um modelo para eles usando um intervalo de confiança.

## Enunciado da atividade

Nesta atividade, você vai escolher algum fenômeno à sua volta que possa ser modelado por uma distribuição Binomial, Poisson ou Exponencial. Você **não pode** repetir o mesmo fenômeno da APS 4. Você **deve ser capaz de** observar o fenômeno várias vezes (no mínimo 10).

A atividade consiste em observar o fenômeno que você escolheu por diversas vezes, estimar os parâmetros do modelo ($p$ para Binomial, $\lambda$ para Poisson, $\mu$ para Exponencial) para cada observação, e então estimar um intervalo de confiança para esse parâmetro.

Para isso, siga os seguintes passos:

1. Escolha um fenômeno à sua volta ou a que você tenha acesso e explique porque ele pode ser modelado por uma Binomial, Poisson ou Exponencial. Em especial, explique quais fenômenos são *independentes entre si.*
2. Colete dados sobre seu fenômeno em diversas observações independentes. Lembre-se de conseguir *pelo menos 10 observações*. Se não achar dados, ou julgar que não conseguirá coletá-los em tempo hábil, guarde essa ideia para depois, volte ao passo 1 e escolha outro fenômeno.
3. Estime os parâmetros do modelo em para cada uma das observações.
4. Usando o Teorema Central do Limite, estime a distribuição para a média dos parâmetros que foram calculados no ítem anterior.
5. Com base nos resultados do ítem anterior, encontre um intervalo de confiança de 95% para o parâmetro que você estimou.
6. Interprete seu intervalo de confiança em relação ao problema.

### Exemplo:

1. Estou observando o número de pessoas que frequentam um horário de atendimento. Para isso, escolho a distribuição Poisson porque cada aluno vem independemente, e estou lidando com a média de alunos por hora.
2. Observei 10 horários de atendimento, e a presença foi de $2, 4, 3, 5, 2, 4, 3, 2, 1, 4$ alunos.
3. Meu parâmetro $\lambda_n$ para cada observação igual ao número de alunos que veio ao atendimento
4. Pelo TCL, $\bar{\lambda} \sim N(\lambda, \lambda/10)$
5. Meu intervalo de confiança para $\lambda$ é encontrado usando a `ppf` da Normal com média $\bar{\lambda}$ e variância $\bar{\lambda}/10.$ Descubro, então, que meu intervalo de confiança para $\lambda$ vai de $2.4$ a $4.6$.
6. Isso significa que a média de atendimentos está entre 2.4 e 4.6, mas não quer dizer que a probabilidade de ter 5 atendimentos é baixa: o intervalo de confiança diz respeito a $\lambda$ e não aos valores da PMF da distribuição!

### Importante: como calcular o desvio padrão $\sigma$ que será usado no TCL:

Lembre-se que o intervalo de confiança obtido com o TCL diz respeito ao parâmetro medido. Porém, o desvio padrão da distribuição nem sempre diz respeito a esse parâmetro! Use as regras abaixo:

* Binomial: `sigma_p = st.binom.std(n, p)/n`, porque o desvio padrão diz respeito a $k$ , mas queremos estimar o parâmetro $p=k/n$.
* Poisson: `sigma_lambda = st.poisson.std(L)`, porque o desvio padrão diz respeito à própria contagem de eventos que é $\hat{\lambda}$.
* Exponencial: `sigma_mu = st.expon.std(scale=mu)`, porque o desvio padrão diz respeito à média de intervalos entre eventos que é $\hat{\mu}$.


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
2. Título do trabalho, que deve ser algo como "Entendendo o fenômeno X (seu fenômeno escolhido) usando modelo (seu modelo)" (parafraseie isso!)
3. Um texto explicando todos os ítens do desenvolvimento com detalhe suficiente para permitir que alguém de outra turma desta disciplina possa reproduzir o mesmo experimento e criticá-lo.
4. Inclua no texto uma tabela com os dados que foram coletados!
5. Uma auto-avaliação da do texto, justificando a nota que foi auto-atribuídas.

# Rubricas e avaliação

Cada um dos ítens (exceto a auto-avaliação) será avaliado da seguinte forma:

| Rubrica | Descrição                                                                                                                                                                                                                                                                                                                                                            | Exemplo                                                                                                                                                              |
| ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| F       | Não entregue, entregue fora do prazo, entregue fora do escopo ("fiz outra coisa")                                                                                                                                                                                                                                                                                     | Não entregar                                                                                                                                                        |
| E       | Entregue no prazo e dentro do escopo, mas a entrega tem um ou mais ítens faltando ou só é compreensível se for acompanhado deste enunciado (por exemplo, ao dizer "resposta ao ítem 2" ao invés de ter um título explicativo) ou está ilegível (exemplo: textos sem sentido ou figuras muito grandes / muito pequenas ou em resolução baixa)                | Colocar no título de uma figura: "ítem 1a"                                                                                                                         |
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
