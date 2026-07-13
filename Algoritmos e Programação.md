## 1 - Introdução à Lógica de Programação

O termo lógica está profundamente ligado à **coerência** e à **racionalidade**, sendo uma de suas responsabilidades, **determinar se uma operação é ou não é válida**. A lógica de programação utiliza esta estrutura de pensamento na **programação de computadores**, principalmente através da construção de **algoritmos**.
Os **algoritmos** são **conjuntos finitos de etapas** que devem ser executadas para a realização de uma **tarefa**, e.g., uma receita de bolo que traz os ingredientes e os passos para o seu preparo.
No contexto da programação de computadores, os algoritmos são utilizados para dizer ao computador as **instruções** que devem ser realizadas para que um determinado problema seja resolvido. Sua finalidade é a **representação** mais fiel **do raciocínio envolvido na lógica de programação**.

### Contrução de Algoritmos

A construção de algoritmos é um **passo importante**, pois uma vez compreendido seu funcionamento, este pode ser **traduzido para qualquer linguagem de programação**. Para se construir um algoritmo, devem ser seguidos os seguintes passos:
1. **Compreender o problema** e definir os pontos mais importantes;
2. **Definir os dados de entrada**, i.e., os dados que serão inseridos no computador;
3. **Definir o processamento desses dados**, i.e., através de que operações o computador processará esses dados;
4. **Definir os dados de saída**, i.e., os dados que serão retornados pelo computador;
5. **Construir o algoritmo** propriamente dito.
Para a construção do algoritmo, temos três tipos de representações mais utilizadas:

#### Linguagem natural

Consiste em analisar o programa e descrever os passos a serem seguidos para sua solução utilizando linguagem natural, i.e., a nossa **língua nativa**, que utilizamos para nos comunicar uns com os outros. Ex:

> Passo único: escreva “Olá, Mundo!” na tela do usuário
> 

#### Fluxograma

Trata-se da descrição dos passos para a solução de um problema utilizando **símbolos gráficos pré-estabelecidos**. Ex:



![Exemplo de flugrama para escrever uma saudação na tela](untitled.png)

Exemplo de flugrama para escrever uma saudação na tela

![Simbologia utilizada em fluxogramas](Untitled%201.png)

Simbologia utilizada em fluxogramas

#### Pseudocódigo

Trata-se da descrição dos passos para a resolução de um problema utilizando-se **regras prefedinidas**. É o método que nos permite representar o fluxo de execução do nosso algoritmo com **maior clareza**. Um exemplo desse tipo de pseudocódido é o Portugol. Ex:

```text
ALGORITMO "OlaMundo"
INICIO
    ESCREVA ("Olá, Mundo! ")
FIMALGORITMO
```


### Linguagens de Programação e Programas

Uma linguagem de programação é um **método padronizado por regras sintáticas e semânticas de implementação de um código fonte** para a criação de um programa de computador.
Um programa de computador nada mais é do que um **conjunto de instruções a serem seguidas** pelo computador para a realização de uma tarefa, i.e., é a **implementação de um algoritmo** em alguma linguagem de programação.
Esse exemplo da saudação pode ser transcrito para linguagens de programação como Pascal, C ou Java, como é possível ver nos exemplos a seguir:


```pascal
  PROGRAM OlaMundo;
  BEGIN
    WRITELN('Olá, Mundo! ');
  END. 
```

```c
    #include <stdio.h>
    
int main()
{
    printf("Olá, Mundo! \n");
    return 0;
}
```

```java
public class OlaMundo{
    public static void main(String[] args){
        System.out.println("Olá, Mundo! ");
    }
}
```


### Entrada e Saída

- Os **dados que serão inseridos** no computador para que ele possa processá-los são a nossa **entrada**. Para a obtenção desses dados são utilizados os **comandos de entrada**.
- Os **dados que são retornados** pelo computador após o processamento são chamados de **saída**. Para a entrega desses dados são utilizados os **comandos de saída**.
- As formas mais comuns de entrada e saída de dados são, respectivamente, os valores digitados pelos usuários e os dados exibidos na tela pelo computador.

### Tipos de Dados

Do ponto de vista computacional oa dados se dividem em três tipos:

- **Tipo numérico**: se subdivide em:
    - **Tipo inteiro**: aceita dados numéricos **inteiros**: positivos, negativos ou zero. Ex: 1, 34, 720;
    - **Tipo real**: aceita dados numéricos **reais: inteiros ou fracionários**, positivos, negativos ou zero. Esses números são representados seguindo-se a notação inglesa, separando-se a parte inteira da fracionária por “.”, por isso, esses dados são chamados também de **números de ponto flutuante** (*floating point numbers*). Ex: 0.3, 5.0, 154.25.
- **Tipo literal**: aceita **caracteres**, i.e., letras, números e símbolos especiais. Ex “a”, “3”, “F”, “@”, “_”.
- **Tipo lógico ou booleano**: representam apenas dois valores possíveis: **verdadeiro ou falso**.

## Variáveis e constantes

Um programa utiliza **espaços da memória** do computador para o **armazenamento dos dados** que serão, foram ou estão sendo processados. Totos os dados armazenados pelo computador, o são em **formato numérico binário**, i.e., através de zeros (0) e uns (1), inclusive letras e outros caracteres.
**Variáveis e constantes são endereços da memória** do computador que possuem **identificador** (nome), **tipo** e **valor**, com cada uma delas podendo armazenar somente um valor de cada vez. A diferença entre elas é que a **variável permite que seu valor seja alterado** no decorrer do processamento, enquanto que a constante não.

```pascal
PROGRAM EntradaESaida;
VAR
	// Declaração de variáveis
	idade: Integer;
	salario: Real;
	nome: String;
(* Os tipos de dados em Pascal são Integer (número inteiro),
 Real (número real), Char (um caractere), String (encadeamento
 de caracteres) e Boolean (dado lógico) *)
BEGIN
	//Entrada de dados
  READLN (nome);
  READLN (idade);
  READLN (salario);
	// Saída de dados
  WRITELN ('nome: ', nome);
  WRITELN ('idade: ', idade);
  WRITELN ('salario: ', salario);
END.
```

### Operadores

São componentes que nos permitem **processar os dados** no decorrer do nosso programa.

#### Operador de Assimilamento

O operador de assimilamento (:= ou =) **atribui à variável** à sua esquerda **o valor** à sua direita

#### Operadores Aritméticos

Permitem a realização de operações aritméticas, como adição, subtração, divisão etc:
- **Adição**: +
- **Subtração**: -
- **Multiplicação**: *
- **Divisão**: /
- **Módulo ou Resto da Divisão**: MOD ou %
- Seguem a seguinte ordem de precedência:
- Operações entre parênteses;
- Mutiplicação, Divisão e Módulo da Divisão;
- Adição e Subtração.

#### Operadores Relacionais

Permitem a comparação entre dois valores:
- **Igualdade** (= ou \==): verifica se dois valores são iguais;
- **Desigualdade** (<> ou !=): verifica se dois valores são diferentes;
- **Maior que** (>): verifica se o valor à sua esquerda é maior que o valor à sua direita;
- **Menor que** (<): verifica se o valor à sua esquerda é menor que o valor à sua direita;
- **Maior que ou igual a** (>=): verifica se o valor à sua esquerda é maior ou igual ao valor à sua direita;
- **Menor que ou igual a** (<=): verifica se o valor à sua esquerda é menor ou igual ao valor à sua direita.

Os operadores aritméticos têm precedência sobre os operadores relacionais.

#### Operadores Lógicos

Permitem associar expressões que estabelecem comparações entre valores:
- **E** (AND ou &&): retorna verdadeiro se ambos operandos forem verdadeiros;
- **OU** (OR ou ||): retorna verdadeiro se pelo menos um dos operandos for verdadeiro;
- **NÃO** (NOT ou !): retorna verdadeiro se o valor for falso e falso se este for verdadeiro.

Obedecem à seguinte ordem de precedência: NOT - AND - OR
 
Os operadores obedecem à seguinte ordem de precedência:
- Parênteses mais internos
- Operador NÃO
- Multiplicação, divisão e módulo
- Adição e subtração
- Operadores relacionais
- Operador E
- Operador OU
- Operadores de assimilação

Em Pascal o operador AND tem a mesma precedência dos operadores \*, / e MOD e o operador OU dos operadores + e -.

```pascal
PROGRAM Operators;
VAR a, b, c: Integer;
BEGIN
	a := 4 + 1; //5
	b := -3;
	c := a + b * 2; // -1
	WRITELN(a > (b * c)); // VERDADEIRO
	WRITELN((c <= a) AND (b > c)); // FALSO
	WRITELN((a < b) OR (c <> 0)); // VERDADEIRO
END.
```

### Estrutura Sequencial

Quando um algoritmo é executado, este segue uma **estrura linea**r, de cima para baixo e da esquerda para a direita, i.e., **as ações são executadas na mesma ordem em que foram escritas.** **Cada ação é separada da próxima por um ponto e vírgula** (;), i.e., sempre que o algoritmo encontra um ; ele entende que o aquele comando foi encerrado e o que vem a seguir é um novo comando.
Esta ordem seguêncial de execução do algoritmo pode, no entanto, ser alterada, permitindo que um determinado bloco de código seja executado somente se uma condição for safisteita, ou que que outro bloco seja repetido diversas vezes.

---
## 2 - Estruturas de Seleção

As estruturas de seleção **nos permitem escolher executar um determinado bloco de código quando uma condição**, representada por expressões lógicas ou relacionais, **é ou não satisfeita**, i.e., elas permitem decidir qual caminho nosso algoritmo seguirá com base em um teste lógico.

### Estrutura de Seleção Simples

É utilizada para testar uma condição antes de executar uma ação e, SE (*IF*) ela retornar um valor verdadeiro, ENTÃO (*THEN*) o bloco de código é executado, caso contrário, o fluxo de execução seguirá após o fim deste bloco.

```pascal
   IF ( a > 9) THEN WRITELN('a é maior que 9');
```   

### Estrutura de Seleção Composta

- Este tipo de estrutura de seleção é utilizada quando houver alternativas diferentes que dependam da mesma condição: SE (*IF*) ela retornar um valor verdadeiro, ENTÃO (*THEN*) um bloco de código é executado, SENÃO (*ELSE*), outro bloco diferente é executado.

```pascal
IF (a > 10)
    THEN WRITELN('a é maior que 10')
    ELSE WRITELN('a é menor ou igual a 10');
```


### Estrutura de Seleção Aninhada

-É caracterizada pelo agrupamento de várias seleções, sendo normalmente utilizado quando uma combinação de condições deve ser safisteita para que o bloco de código seja executado.

```pascal
IF (a > b) THEN
BEGIN
    IF (a > c)
    	THEN WRITELN('a é maior que b e c')
    	ELSE WRITELN('a é maior que b mas não é maior que c');
END
ELSE WRITELN('a não é maior que b');
```


### Estrutura de Seleção de Múltipla Escolha

É utilizada quando um programa possui diversas opções de execução. Este tipo de seleção pode ser feita através da sucessão de estruturas de seleção SE ou através da estrutura CASO (*CASE*), que permite testar um valor definindo alvos a serem atingidos para que cada opção de código possa ser executada, podendo-se também adicionar uma instrução a ser executada caso senhum dos alvos seja atingido.

```pascal
// Sucessão de SE'S
IF (a = 1) THEN WRITELN('a é igual a 1')
ELSE IF (a = 2) THEN WRITELN('a é igual a 2')
ELSE IF (a = 3) THEN WRITELN('a é igual a 3')
ELSE WRITELN('a é não é igual a 1, nem a 2, nem a 3');
    
// Estrutura CASO
CASE b OF
    1 : WRITELN('b é igual a 1');
    2 : WRITELN('b é igual a 2');
    3 : WRITELN('b é igual a 3');
    ELSE WRITELN('b é não é igual a 1, nem a 2. nem a 3');
END;
```

Em muitas linguagens, como é o caso do C, a estrutura CASO recebe outros nomes como ESCOLHA (s*witch*), no qual há instruções para cada CASO (*case*), i.e., cada possível valor, e uma para um valor PADRÃO (*default*), caso nenhum deles seja atingido.

```c
if (a == b)
    printf("a é igual a b \n");
else
    printf("a é diferente de b \n");

switch (c)
{
    case 1:
    	printf("c é igual a 1");
    	break;
    case 2:
    	printf("c é igual a 2");
    	break;
    case 3:
    	printf("c é igual a 3");
    	break;
    default:
    	printf("c é não é igual a 1, nem a 2, nem a 3");
}
```

---
## 3 - Estruturas de Repetição

As estruturas de repetição **permitem que um mesmo bloco de código seja executado mais de uma vez**, com o número de repetições podendo ser fixo ou estar vinculado a uma deteminada condição, podendo ser **indeterminado**, mas **não infinito**. As estruturas que permitem a criação deste tipo de algoritmo são chamadas de laços de repetição ou *loops*.

### Estrutura ENQUANTO

Esta estrutura permite que um bloco de código seja executado ENQUANTO (*WHILE*) uma determinada condição retorna verdadeiro.

```pascal
a := 2;
WHILE a < 100
    DO a := 2 * a;
WRITELN(a); // 128
```


### Estrutura FAÇA/ ENQUANTO

Em algumas linguagens, como o C, esta estrutura está presente. Ela indica ao algoritmo que FAÇA (*do*) uma ação, i.e., que execute um determinado bloco de código, ENQUANTO (*while*) uma condição for verdadeira. A principal diferença desta estrutura para a estrutura ENQUANTO é que o bloco de código é executado a primeira vez, e só então a condição é testada, i.e., o código **é executado pelo menos uma vez,** mesmo que a condição já seja falsa.

```c
int a = 2;
do
{
    a *= 2;
} while (a < 100);

printf("%d", a); // 128
```

### Estrutura REPITA/ ATÉ QUE

Em outras linguagens, como o Pascal, existe esta estrutura, que permite que se REPITA (*REPEAT*) a execução um determinado bloco de código ATÉ QUE (*UNTIL*) uma determinada condição seja satisfeita. Assim como a estrutura FAÇA/ ENQUANTO, esta estrutura **executa o código pelo menos uma vez**, a diferença é o loop é executado **enquanto a condição retorna um valor falso**.

```pascal
a := 2;
REPEAT
    a := 2 * a;
UNTIL a > 100;

WRITELN(a); // 128
```

### Estrutura PARA/ ATÉ

Esta estrutura permite repetirmos um bloco de código um número específico de vezes PARA (*FOR*) uma variável que vai de um valor $x$ ATÉ (*TO*) um valor $y$.

```pascal
a := 2;
FOR i := 1 TO 6
    DO a := 2 * a;
WRITELN(a); // 128
```

---
## 4 - Vetores e Matrizes

Um vetor ou array é uma **sequência de valores do mesmo tipo, referenciadas por um identificador** (nome) **único**.

```pascal
VAR
    nums: ARRAY [1..10] OF Integer = (10, 20, 30, 40, 50, 60, 70, 80, 90, 100);
```

```c
int nums[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 10};
```

Os valores armazenados dentro de um vetor **são armazenados na memória do computador de forma sequencial**, i.e., um após o outro. Assim, **cada elemento pode ser acessado** **com o auxílio de um** número inteiro dado como **índice**.

```pascal
VAR
    nums: ARRAY [1..10] OF Integer = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
BEGIN
    WRITELN(nums[5]); // 5
    nums[7] := 0;
    WRITELN(nums[7]); // 0
END.
```

Algumas linguagens como o C, tem seus vetores **indexados a partir da posição 0**, i.e., o primeiro valor dentro do vetor é acessado pelo índice 0 e último pelo índice $n-1$, em um vetor no qual $n$ é o seu número de elementos.

```c
int nums[5] = {1, 2, 3, 4, 5};
printf("%d\n", nums[0]); // 1
printf("%d\n", nums[4]); // 5
```

Outras linguagens, como a Lua, tem seus elementos indexados a partir da posição 1, sendo o primeiro item acessado pelo índice 1 e o último pelo índice $n$, em um vetor com $n$ elementos. Outras como o Pascal permitem indexar um array com qualquer tipo de dado enumerado, permitindo-nos escolher o indíce inicial do vetor.

```pascal
VAR
    nums1: ARRAY [0..9] OF Integer;
    nums2: ARRAY [1..10] OF Integer;
```

Como um vetor é um conjunto de valores do mesmo tipo acessados através do mesmo identificador, uma matriz é um conjuntos de vetores acessados pelo mesmo identificador, i.e., **uma matriz é um vetor de vetores ou um vetor multi-dimensional**. Cada elemento da matrix pode ser acessado através de um índice para cada uma das dimensões dela, e.g., para um vetor bidimensional utilizamos 2 índices para acessar cada elemento.

```pascal
VAR
    matrix: ARRAY [0..2, 0..2] OF Integer;
BEGIN
    matrix[0][0] := 1;
    WRITELN(matrix[0][0]); // 1
END.
```
    
```c
int matrix[3][3];
matrix[0][0] = 1;
printf("%d\n", matrix[0][0]); // 1
```

Podemos utilizar loops para percorrermos um vetor ou uma matriz, i.e., acessarmos cada um de seus elementos.

```pascal
VAR
    matrix: ARRAY [0..2, 0..2] OF Integer;
    count, row, col: Integer;
BEGIN
    count := 1;
    FOR row := 0 TO 2 DO
    BEGIN
    	FOR col := 0 TO 2 DO
    	BEGIN
    		matrix[row][col] := count;
    		count := count + 1;
    	END;
    END;
    WRITELN(matrix[1][1]); // 5
END.
```

```c
int matrix[3][3];
int count, row, col;
count = 1;
for (row = 0; row < 3; row++)
    for (col = 0; col < 3; col++)
    	matrix[row][col] = count++;
printf("%d", matrix[1][1]); // 5
```