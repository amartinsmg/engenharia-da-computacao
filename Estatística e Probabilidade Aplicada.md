# 1 - Conceitos Básicos da Estatística

- **Estatística** é a ciência que se dedica a coletar, organizar, resumir, analisar e apresentar **dados**, que nada mais são do que conjuntos de observações. Estes dados podem subdivididos em diferentes tipos:
    - **Qualitativos:** identifica alguma qualidade, categoria ou característica, que não possa ser medida mas classificada.
    - **Quantitativos**: identifica características que podem ser medidas com diferentes intensidades. Se subdividem em:
        - **Discretos**: assumem valores numéricos naturais e representam contagem.
        - **Contínuos**: podem assumir quaisquer valores numéricos reais, associados a uma escala contínua, representando mensuração (medida).
- O conjunto de indivíduos estudados em uma pesquisa é chamado de **população**, cujos subconjuntos são chamados de **amostra**. A coleção de dados relativos a todos os elementos de uma população é chamado de **censo**.

## Ferramentas Gráficas

- Dentre as ferramentas que utilizamos para a análise e apresentação dos dados estão os **gráficos**, que nos permitem compilar de maneria clara o **comportamento e a relação das variáveis estudadas**. Dentre os tipos de ferramentas que mais utilizamos temos:
    - **Histograma**: utilizado para a analise da frequência (absoluta ou relativa) de dados quatitativos, distribuidos em classes, os quais podem ser representados em barras ou colunas
    - **Polígono de frequência**: gráfico de linha obtido através da conexão dos pontos médios de cada uma das classes de um histograma
    - **Ogiva**: gráfico de linha que exibe a frequência acumulada das classes de um histograma
    - **Gráfico de barras**:: utilizados para a análise de dados qualitativos, apresentados no eixo vertical, cuja frequência (absoluta ou relativa) é dada no eixo horizontal.
    - **Gráfico de colunas**: muito semelhante ao gráfico de barras, com a diferença que os dados qualitativos analisados são apresentados no eixo horizontal, enquanto que a sua frequência é dada no eixo vertical
    - **Gráfico de setores (ou de pizza)**: utilizado para a análise de dados qualitativos representados por cada setor, cuja área representa a frequência relativa deste dado.
    - **Gráfico de dispersão**: utilizado para a análise de dados quantitativos, no qual cada eixo representa uma variável diferente

## Medidas de Tendência Central

Buscam resumir todo o conjunto em um único número, que busca ser um ponto de equilíbrio dos dados.

- **Média**: dada pela fórmula abaixo na qual $x_{i}$ representa cada elemento e $n$ é o número total de elementos.
    
    $$
    {\mu} = \frac{\sum_{i=1}^{n} {x}_{i}}{n}
    $$
    
    - **Média Ponderada**: usada quando cada elemento possui um peso diferente. É dada pela fórmula abaixo na qual $x_{i}$ representa cada elemento, $w_{i}$ representa seu respectivo peso e $n$ o número total de elementos.
        
        $$
        {\mu} = \frac{\sum_{i=1}^{n} {x}_{i}{w}_{i}}{\sum_{i=1}^{n} {w}_{i}}
        $$
        
- **Mediana**: é o **valor central** de um conjunto de dados ordenados (em ordem crescente ou decrescente). Se o número de dados do conjunto for ímpar a mediana é dada pelo valor central, se o número de dados for par, a mediana é dada pela média dos valores centrais
- **Moda**: é o valor (ou os valores) que **mais se repete** em um conjunto de dados. Caso não haja um valor mais frequente no conjunto, este é denominado amodal.

## Medidas de Dispersão

São indicadores do nível de variação dos dados.

- **Amplitude**: é dada pela **diferença entre o maior e o menor** elemento de um conjunto de dados.
    
    $$
    {A}={x}_{maior}-{x}_{menor}
    $$
    
- **Variância**: mostra o **quão distante cada valor está do valor médio** (média) do conjunto. É dada pelas seguintes fórmulas, onde $\mu$ representa a média e $x_{i}$ cada valor do conjunto de dados:
    
    $$
    \text{Variância da amostra:}\\
    {\sigma}^{2} = \frac{\sum_{i=1}^{n} {({x}_{i}-{\mu})}^{2}}{n-1}\\\space\\
    \text{Variância da população:}\\
    {\sigma}^{2} = \frac{\sum_{i=1}^{n} {({x}_{i}-{\mu})}^{2}}{n}
    $$
    
- **Desvio Padrão**: mostra o **quão “confiável” é a média**, i.e., mostra o “erro” dela ao representar o conjunto de dados. Quanto maior o desvio padrão, menos “confiável” é a média, i.e., mais distantes os dados estão dela. É dado pelas seguintes fórmulas, onde $\mu$ representa a média e $x_{i}$ cada valor do conjunto de dados:
    
    $$
    \text{Desvio Padrão da amostra:}\\
    {\sigma} = \sqrt{\frac{\sum_{i=1}^{n} {({x}_{i}-{\mu})}^{2}}{n - 1}}\\\space\\
    \text{Desvio Padrão da população:}\\
    {\sigma} = \sqrt\frac{\sum_{i=1}^{n} {({x}_{i}-{\mu})}^{2}}{n}
    $$
    

# 2 - Análise Combinatória e Probabilidade

## Princípio Fundamental da Contagem

A forma mais básica de realizarmos uma análise de possíveis ocorrências de um determinado fenômeno é através do **Princípio Fundamental da Contagem**, segundo o qual, se um evento é composto por duas ou mais etapas sucessivas e independentes, o número de combinações possíveis é dado pelo produto entre as possíbilidades de cada conjunto.

## Permutações, Arranjos e Combinações

- A **permutação** é utilizada quando queremos contar o número de possibilidades de formação de uma sequência (na qual a **ordem dos elementos é importante**) que contenha todos os elementos de um determinado conjunto com $n$ elementos. Sua fórmula é:
    
    $$
    {P}_{n} = {n}!
    $$
    
- O **arranjo** é utilizado para contarmos o número de possibilidades de formação de uma sequência (na qual a **ordem dos elementos é importante**) de $p$ elementos tomados a partir de um conjunto com $n$ elementos. Sua fórmula é:
    
    $$
    {A}_{(n, p)} = \frac{n!}{(n - p)!}
    $$
    
- A **combinação** é utilizada para contarmos o números de possibilidades de formação de subconjuntos (nos quais a **ordem dos elementos NÃO é importante**) de $p$ elementos tomados a partir de um conjunto com $n$ elementos. Sua fórmula é:
    
    $$
    {C}_{(n, p)} = \binom{n}{p} = \frac{n!}{p!\cdot(n - p)!}
    $$
    

## Probabilidade

É utilizada quando desejamos mensurar a **chance de ocorrência** de algo. Para podermos trabalhar melhor com ela precisamos conhecer alguns conceitos:

- **Experimento aleatório:** é aquele experimento que tem um conjunto bem determinado de resultados possíveis, **não podendo ter seu resultado previsto antes de sua realização. E**m cotraposição existem os eventos determinísticos, cujo resultado é sempre o mesmo, conservando-se a condição ou estado inicial.
- **Espaço Amostral ($\Omega$)**: ****conjunto de todos os resultados possíveis de um experimento aleatório.
- **Evento**: é qualquer subconjunto contido do espaço amostral.
    - Quando um evento é composto por um conjunto vazio ele é chamado de **evento impossível.**
    - Quando os elementos de um evento correspodem ao próprio espaço amostral dizemos que trata-se de um **evento certo.**
    - Dizemos que dois eventos são **complementares** quando a intersecção entre eles forma um conjunto vazio e a união deles resulta no próprio espaço amostral, i.e., quando eles não possum elementos em comum, mas todos os possíveis resultados do experimento pertencem a um destes eventos.
        
        $$
        {A}\cup{B} = \Omega\\ {A}\cap{B} = \varnothing
        $$
        
- **Cálculo da probabilidade de um evento** $A$ ( $P(A)$): é dado pela **razão do número de elementos do evento $A$ pelo número de elementos do espaço amostral**. O resultado sempre será um número maior ou igual a zero e menor ou igual a um, sendo um evento com probabilidade igual a 0, um evento impossível, e o evento com probabilidade igual a 1, um evento certo.
    
    $$
    {P(A)}=\frac{n(A)}{n(\Omega)}\\ \text{onde }{0}\ge{P(A)}\le{1}\\\space\\
    \text{se } A = \varnothing \text{ então } {P(A)} = 0\\
    \text{se } A = \Omega \text{ então } {P(A)} = 1
    $$
    

### Probabilidade Condicional

- É a probabilidade de ocorrência de um evento $A$ **dado que o evento** $B$ **já ocorreu**. É dada pela fórmula:
    
    $$
    {P(A|B)}=\frac{P({A}\cap{B})}{P(B)}
    $$
    
- Se $A$ e $B$ são eventos **independentes**, i.e., se a ocorrência de um NÃO afeta a chance da ocorrência de outro, temos que:

$$
{P({A}\cap{B})}={P(A)}\cdot{P(B)}\\\space\\
\text{Logo }{P(A|B)} = {P(A)}
$$

# 3 - Distribuição de Probabilidade Discreta

Uma variável aleatória é uma variável **quantitativa** cujo resultado depende de **fatores aleatórios**, e para cada variável aleatória pode-se relacionar uma distribuição de probabilidade. Uma **variável aleatória discreta** tem seus **possíveis valores** descritos por uma distribuição de probabilidade discreta.

## Distribuição de Bernoulli

- É a distribuição discreta de espaço amostral {0, 1} em que 0 representa fracasso e 1, sucesso. Sendo $x$ uma variável aleatória com esta distribuição, temos a seguinte função de probabilidade em que $p$ é a probabilidade de sucesso, i.e., de $x = 1$:
    
    $$
    P(x) = p^{x} \cdot q^{1-x}\\
    \text{onde } q = (1-p)
    $$
    

## Distribuição Binominal

- É a distribuição discreta que representa o número de sucessos numa sequência de $n$ tentativas,  tais que:
    - Cada tentativa têm apenas dois resultados possíveis: sucesso ou fracasso;
    - Cada tentativa é independente;
    - A probabilidade de sucesso ($p$) , premanece constante em todas as tentativas;
    - O número de tentativas é finito.
- Se a variável aleatória $x$ tem essa distribuição temos que:
    
    $$
    {P(x)}= \binom{n}{x} \cdot {p}^{x}\cdot{q}^{n-x}
    $$
    
    Onde $n$ é o número de tentativas realizadas, $p$ é a probabilidade de sucesso e $q$ a probabilidade de fracasso:
    
- Para esse tipo de distribuição temos que:
    
    $$
    \mu = np\\
    \sigma^2 = npq\\
    \sigma = \sqrt{npq}
    $$
    

## Distribuição de Poisson

- É a distribuição de probabilidade discreta que representa a probabilidade de ocorrência de um evento aleatório num dado intervalo de tempo, independente de quando ocorreu o último evento.
    
    $$
    Poisson = \lim_{n \to \infty}Binomial
    $$
    
- Sendo $x$ uma variável aleatória que tenha essa distribuição, temos que:
    
    $$
    P(x) = \frac{{\lambda}^{x} \cdot e^{-\lambda}}{x!}
    $$
    
    Onde $\lambda$ é o número esperado de ocorrências num dado intervalo de tempo, e $e$ é a base o logaritmo natural ou número de Euler, cujo valor é aproximadamente 2.7182818…
    

# 4 - Distribuição de Probabilidade Contínua

Uma distribuição de probabilidade contínua descreve as probabilidades dos possíveis valores de uma **variável aleatória contínua**.

### Distribuição Normal ou Gaussiana

- Trata-se de uma distribuição de probabilidade contínua que é parametrizada pela média ou esperança matemática ($\mu$) e desvio padrão ($\sigma$) e obedece à seguinte fórmula:
    
    $$
    \phi(x)=\frac{e^{-\frac{1}{2}(\frac{x-\mu}{\sigma})^2}}{\sqrt{2\pi}}
    $$
    
    Em que $x$ é uma variável aleatória contínua distribuída normalmente.
    
- Essa distribuição possui a seguinte função para a probabilidade cumulativa, que representa a probabilidade uma uma variável aleatória $X$ ser menor ou igual a um valor $x$:
    
    $$
    P(X \le x) = \Phi(x) = \int_{-\infty}^{x} \phi(x) dx 
    $$
    
- Esta distribuição de probabilidade é muito utilizada para descrever fenômenos naturais, uma vez que muitos desses fenômenos apresentam uma distribuição de probabilidade tão proximamente normal que são representados como se fossem normais.
- Uma característica marcante nessa distribuição de probabilidade é o gráfico em forma de sino e a simetria deste em torno da média ($\mu$):
    
    ![Untitled](normal-distribution.png)
    
    A lei que define a curva dessa distribuição de probabilidade depende da média ($\mu$) e do desvio-padrão ($\sigma$). Mas, independentemente dos valores destes parâmetros, a curva sempre mantém a forma de sino e a área sob ela é sempre igual a 1, garantindo a correspondência entre esta **área e a probabilidade**.
    
- Para cada valor $x$ com distribuição de probabilidade normal, temos um **escore-**$z$  correspondente, que indica quantos **desvios padrão** este valor **dista da média**.
- Quando uma distribuição normal possui média nula ($\mu = 0$) e desvio padrão unitário ($\sigma = 1$) esta é chamada de **distribuição normal padrão**. Para esse tipo de distribuição, o valor de $x$ é igual ao do escore-$z$ correspondente ($x = z$).
- Para distribuições normais não padronizadas, i.e., com média não nula ($\mu \ne 0$) ou desvio padrão não uniátio ($\sigma \ne 1$), podemos utilizar as seguintes fórmulas para convertermos um valor de uma variável aleatória $x$ distribuída normalmente em escore-$z$ ou vice-versa:
    
    $$
    z = \frac{x - \mu}{\sigma}\\
    \space\\
    x = \mu + z \cdot \sigma
    $$
    
- Para a determinação da área sob a curva delimitada (à direita) por um escore-$z$ (i.e. a área à esquerda deste escore $z$) e, por conseguinte, a sua probabilidade, podemos utilizar a seguinte tabela:

[Tabela da Distribuição Normal Padrão.pdf](Tabela_da_Distribuio_Normal_Padro.pdf)