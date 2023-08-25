# APS 02 - Classificação de Textos

Uma das aplicações do Teorema de Bayes é fazer classificadores de textos. Eles servem para identificar intenções de usuários em chatbots, encontrar linguagem maliciosa, e também para separar spam em e-mails.

## Classificando usando uma única palavra

Uma das maneiras de classificar textos é descobrir se ele contém uma determinada palavra. Por exemplo, se queremos classificar uma letra de música entre "rock" ou "axé", talvez possamos procurar pela palavra "agito". Veja, nesse caso, temos duas probabilidades:

$$
P(\text{rock} | \text{agito}), \text{ e}\\
P(\text{axé} | \text{agito})
$$

Poderíamos estimar essas probabilidades à partir de dados - talvez, um grande conjunto de letras de música contendo rock e axé. Usando essas dados, podemos nos perguntar: dentre todas as letras de música que têm a palavra "agito", quantas são letras de rock e quantas são letras de axé?

Uma outra possibilidade é usar o Teorema de Bayes. Nesse caso, precisamos estimar:

* $P(\text{agito} | \text{rock})$, usando a quantidade de músicas que têm a palavra "agito" dentre aquelas que são "rock",
* $P(\text{agito} | \text{axé})$, usando a quantidade de músicas que têm a palavra "agito" dentre aquelas que são "axé",
* $P(\text{agito})$, que é a probabilidade de uma música sorteada aleatoriamente ter a palavra "agito", e
* $P(\text{rock})$ e $P(\text{axé})$, que são as probabilidades de músicas sorteadas aleatoriamente serem de rock ou axé.

Daí, usamos o Teorema de Bayes para estimar:

$$
P(\text{rock} | \text{agito}) = \frac{P(\text{agito}| \text{rock}) P(\text{rock})}{P(\text{agito})}, \text{ e}\\
P(\text{axé} | \text{agito}) = \frac{P(\text{agito}| \text{axé}) P(\text{axé})}{P(\text{agito})}
$$

(Nota: se você não sabe porque essa equação aparece, [veja este vídeo](https://youtu.be/bISWzyi0tDE), e depois [este outro](https://youtu.be/e2tog7ojm04).)

Daí, estimamos que a classe correta (neste caso, o gênero musical correto) é aquele com maior probabilidade, dadas as evidências que coletamos.

É claro que, se não encontrarmos a palavra, devemos fazer as mesmas medidas para a *ausência* da palavra agito, encontrando $P(\text{rock} | \overline{\text{agito}})$ e $P(\text{rock} | \overline{\text{axé}})$.

## Usando mais palavras

Podemos usar mais de uma palavra para fazer nosso classificador. Para isso, podemos assumir, inocentemente, que a ocorrência de palavras é independente para o nosso classificador. Isso significa que a probabildiade de encontrar "agito" e "Sol" simultaneamente é:

$$
P(\text{agito} \cap \text{Sol}) = P(\text{agito})P(\text{Sol}).
$$

Nessas condições, podemos calcular:

$$
P(\text{rock} | \text{agito} \cap \text{Sol}) = \frac{P(\text{agito} \cap \text{Sol}| \text{rock}) P(\text{rock})}{P(\text{agito} \cap \text{Sol})} = 
\frac{P(\text{agito}| \text{rock})}{P(\text{agito})} \frac{P(\text{Sol}| \text{rock})}{P(\text{Sol})} P(\text{rock})
$$

Evidentemente, caso não encontremos uma das palavras, daí deveriamos usar essa informação, encontrando $P(\text{rock} | \text{agito} \cap \overline{\text{Sol}})$, $P(\text{rock} | \overline{\text{agito}} \cap \text{Sol})$ ou mesmo $P(\text{rock} | \overline{\text{agito}} \cap \overline{\text{Sol}})$.

Então, à partir das nossas evidências (a presença ou não de palavras), da hipótese de independência de palavras, e do Teorema de Bayes, conseguimos estimar a probabilidade de uma determinada letra musical ser de algum entre os gêneros que conhecemos.

## Enunciado do exercício

Neste exercício, você receberá um banco de dados com vários reviews de filmes extraídos do [IMDB](https://www.imdb.com/), dividido em duas partes: em uma, há dados rotulados (`treino.csv`) para calcular os parâmetros do seu modelo, e, em outra, há dados sem rótulo (`teste.csv`), que devem ser classificados. Os rótulos indicam se o review é "positivo" ou "negativo".

**Neste exercício, não é permitido usar bibliotecas de aprendizado de máquina como sklearn, pytorch, keras, tensorflow, etc.**

O grupo de trabalho deve:

* Estimar $P(\text{palavra} | \text{classe})$ e $P(\overline {\text{palavra}} | \text{classe})$ para cada palavra e cada classe (positiva/negativa) presente no conjunto de dados,
* Estimar $P(\text{palavra})$ usando o conjunto total de reviews da base de dados,
* Assumindo a independência entre as palavras e a ideia de que, em produção, $P(\text{negativo})=P(\text{positivo})$, usar o Teorema de Bayes e calcular $P(\text{classe} | \text{texto})$
* Usar o classificador que foi estimado para classificar os textos da base de dados não-rotulada
* Usando o PrairieLearn, validar as classificações que foram realizadas. Seu classificador deve ter um índice de acerto mínimo de 75% para ser considerado "aceitável".
* Produzir um texto explicando, em português (e usando equações matemáticas), como o sistema funciona. Não serão aceitos textos que somente replicam o que está sendo feito no código-fonte.
* Montar um fluxograma ou equivalente que sirva de suporte ao texto.


# Entregas esperadas

Você deve entregar, via Blackboard, um arquivo PDF (uma entrega por grupo!) contendo:

1. Nome do grupo
1. Título do trabalho, que deve ser algo como "Classificador Bayesiano de Textos" (parafraseie isso!)
1. O fluxograma pedido acima. 
1. O texto pedido acima.
1. Uma auto-avaliação do par fluxograma-texto, justificando as notas que foram auto-atribuídas.

# Rubricas e avaliação

Cada um dos ítens (exceto a auto-avaliação) será avaliado da seguinte forma:

| Rubrica | Descrição | Exemplo |
| --- | --- | --- | 
| F | Não entregue, entregue fora do prazo, entregue fora do escopo ("fiz outra coisa") | Não entregar |
| E | Entregue no prazo e dentro do escopo, mas a entrega tem um ou mais ítens faltando ou só é compreensível se for acompanhado deste enunciado (por exemplo, ao dizer "resposta ao ítem 2" ao invés de ter um título explicativo) ou está ilegível (exemplo: textos sem sentido ou figuras muito grandes / muito pequenas ou em resolução baixa) | Colocar no título de uma figura: "ítem 1a"
| D | A entrega tem falhas graves de coesão ou coerência que impedem sua compreensão, ou faltam elementos essenciais (título, legenda, rótulos nos eixos), ou o texto deixa de indicar o que são ideias originais e o que são ideias retiradas de outras fontes, ou as ideias/dados são mostrados de forma embaralhada, sem guiar o leitor a um fluxo de pensamento. | Em um texto: "Existe impacto da renda na educação. Isso porque a renda pode estar ligada a condições de estudo. O estudo é essencial para formar seres humanos"
| C | A entrega não tem falhas graves. Todas as fontes de ideias são indicadas. A entrega traz ao menos um elemento errado ou ao menos um elemento supérfluo (que não contribui para a mensagem passada). | Em um texto: "Essa é uma fonte de 100W (Watts, unidade batizada em homenagem a James Watt, inventor da máquina a vapor")
| B | A entrega tem todos os elementos necessários para passar a mensagem, a mensagem é clara, e não há elementos supérfluos. | Título da figura: "Média de desempenho no ENEM 2022 por disciplina por faixa de renda", com rótulo no eixo Y: "Pontos" e rótulo no eixo X: "faixa de renda".
| A | A entrega está correta e o conteúdo mostra ou induz uma análise crítica do contexto ou das implicações dos dados e informações coletadas. | Título da figura: "Desempenho no ENEM diminui com o aumento da renda", com rótulo no eixo Y: "Pontos" e rótulo no eixo X: "faixa de renda".

A auto-avaliação será avaliada da seguinte forma:

| Rubrica | Descrição | Exemplo |
| --- | --- | --- | 
| F | Não entregue, entregue fora do prazo, entregue fora do escopo ("fiz outra coisa") | Não entregar |
| D | Entregue no prazo e dentro do escopo, mas somente copia as rubricas que foram apresentadas, sem relacioná-las com o material apresentado, ou apresenta notas sem argumentar o motivo delas. | "Nota A, pois está correto e o conteúdo induz análise crítica do contexto"
| C | Entregue, mas claramente puxa as notas "para cima" ou "para baixo" sem ter argumentos | Entrega é uma figura sem título, mas auto-avaliação diz: "o título da figura está correto"
| A | Entregue, e argumentado corretamente  | "Nota A porque a passagem `de acordo com Fulano et al.` mostra que os resultados obtidos condizem com a literatura", ou "Nota B, porque a figura tem todos os elementos, embora não tenha nenhuma indicação de uma leitura crítica do contexto.


Para atingir cada nível, é necessário cumprir todos os requisitos do nível anterior. Cada uma das entregas será avaliada individualmente e isoladamente. A nota geral do trabalho será a menor entre as notas das entregas.
