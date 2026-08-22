 
## A Linguagem C

É uma linguagem de alto nível compilada de propósito-geral, estruturada, imperativa e procedural, criada em 1972 por Dennis Ritchie na AT&T Belll Labs para desenvolvimento do sistema operacional Unix. Atualmente continua sendo usada para o desenvolvimento de sistemas operacionais (especialmente *kernels*), *drivers* de dispositivo, compiladores e softwares aplicativos, sendo compativel com quase todas as arquiteturas computacionais.

É uma das linguagens de programação mais populares no mundo do desenvolvimento de software, tendo influenciado dezenas de outras linguagens (como C++, Java, C#, JavaScript, PHP, Python e muitas outras) e estando presente desde de supercomputadores e computadores domésticos a microcontroladores e sistemas embarcados.

Em C, cada comando é delimitado por ponto-e-vírgula (`;`), e cada bloco, por sua vez,  é delimitado por um par de chaves: `{ }`. Isso facilita o agrupamento lógico e a organização visual do código, além de ajudar a delimitar o escopo das variáveis. Linhas inicidas por `#` em C são diretivas para o pré-processador da linguagem, que  realiza alguns processos antes de mandar o código fonte ao compilador. Os comentários são trechos ignorados pelo compilador (muitas vezes eliminados pelo próprio pré-processador) e podem ser usados para explicar o código e se comunicar com outros desenvolvedores. Comentáios de uma única linha começam com `//`, já blocos de comentário são delimitados por `/* ... */`.

### Tipos de Dados Primitivos

O sistema de tipagem de C é considerado fraco, pois permite certas coersões silenciosas, especialmente quando se trabalha com ponteiros. Quanto às demais características do sistema de tipo, pode ser classicada como estática, manifesta e nominal.

A linguagem C conta com apenas 5 tipos básicos de dados:

| **Tipo / Palavra-chave** | **Tamanho Típico** | **O que armazena?**                                                  |
| ------------------------ | ------------------ | -------------------------------------------------------------------- |
| `void`                   | Nenhum             | Indica ausência de valor (retorno de função) ou tipo genérico.       |
| `char`                   | 1 byte             | Números inteiros de -128 a 127 ou um único caractere (tabela ASCII). |
| `int`                    | 4 bytes            | Números inteiros assinalados ($\approx$ -2.14B a 2.14B).             |
| `float`                  | 4 bytes            | Números de ponto flutuante ($\approx$ 6-7 casas de precisão).        |
| `double`                 | 8 bytes            | Ponto flutuante de precisão dupla ($\approx$ 15-17 casas).           |

#### Sequências de Escape

São sequências de caracteres com um valor semântico especial. São normalmente usados para representar caracteres especiais e começam com uma barra invertida `\`. São elas:

| Sequência | Nome / Descrição                        | O que ela faz                                                              |
| --------- | --------------------------------------- | -------------------------------------------------------------------------- |
| **`\n`**  | Nova Linha (_New Line_)                 | Move o cursor para o início da próxima linha.                              |
| **`\t`**  | Tabulação Horizontal (_Tab_)            | Avança o cursor para a próxima parada de tabulação.                        |
| **`\v`**  | Tabulação Vertical                      | Move o cursor para baixo (raramente usado hoje).                           |
| **`\r`**  | Retorno de Carro (_Carriage Return_)    | Move o cursor de volta para o início da linha atual.                       |
| **`\b`**  | Retrocesso (_Backspace_)                | Move o cursor uma posição para trás (apaga o caractere anterior).          |
| **`\f`**  | Alimentação de Formulário (_Form Feed_) | Avança para a próxima página física (usado em impressoras).                |
| **`\a`**  | Alerta / Sinal Sonoro (_Bell_)          | Produz um bipe ou um sinal sonoro no sistema.                              |
| **`\\`**  | Barra Invertida                         | Imprime uma única barra invertida (`\`).                                   |
| **`\'`**  | Aspas Simples                           | Imprime uma aspa simples (`'`).                                            |
| **`\"`**  | Aspas Duplas                            | Imprime uma aspa dupla (`"`).                                              |
| **`\?`**  | Ponto de Interrogação                   | Imprime uma interrogação (evita confusão com _trígrafos_).                 |
| **`\0`**  | Caractere Nulo (_Null_)                 | Indica o fim de uma string (texto) na memória.                             |
| **`\N`**  | Valor Octal                             | Representa um caractere usando até 3 dígitos octais (ex: `\101` para 'A'). |
| **`\xN`** | Valor Hexadecimal                       | Representa um caractere usando dígitos hexadecimais (ex: `\x41` para 'A'). |

#### Modificadores de Tipo

Em C existem os modificadores de tipo que podem ser usados para alterar o signifcado do tipo-base que os sucedem, fazendo com que ele se adapte melhor a diferentes situações. Todos eles podem ser usados com o tipo inteiro e, quando não é especificado um tipo, o compilador infere automaticamente como `int`.

Os modificadores são:

- `signed` – usado para indicar que podem ser armazenados tanto valores positivos quanto negativos. Todos os `int` são `signed` implicitamente. Pode ser usado também com `char`.
- `unsigned` – usado para indicar que só podem ser armazenados valores positivos (dobrando a capacidade de representação da sua magnitude). Também pode ser usado com `char`.
- `short` – usado para indicar que deve ser alocado um espaço menor na memória para este dado. Normalmente usado para representar inteiros de 16 bits.
- `long` – usado para indicar que deve ser alocado um espaço maior na memória para este dado. Pode ser usado também com o tipo `double`.
- `long long` – usado para indicar que deve ser alocado um espaço de pelo menos 8 bytes (64 bits) para esta variável.

### Variáveis

As variáveis e funções em C podem ter seus nomes (identificadores) formados por letras, números e `_` (sublinha), desde que comece por uma letra ou `_`. Certos nomes são reservados pela linguagem e não podem ser usados como identificadores (como `while`, `return` e `int`, por exemplo). Por se tratar de uma linguagem com sensibilidade de caso (*case sensitive*), letras maiúsculas e minusculas são tratadas como distintas nos nomes das variáveis e palavras chaves. I.e., uma variavel chamada `operando` é diferente de outra chamada `OPERANDO` ou `Operando`.

Pra declaramos uma variável ou mais variáveis, desde que tenham o mesmo tipo, usamos a seguinte sintaxe:

```text
tipo lista_de_variaveis;
```

É possível também atribuirmos um valor para uma variável já durante a sua inicialização. Por exemplo:

```c
float a;

// Criação de uma lista de variáveis
float x, y, z;

// Inicialização de variáveis na declaração
unsigned int age = 19;
char letter = 'b';
```

Variáveis criadas dentro de um bloco só podem ser acessadas dentro deste bloco, são chamadas, por isso, de **variáveis locais**. Enquanto que as variáveis declaradas fora de qualquer bloco, e que portanto podem ser acessadas por qualquer parte do programa, são chamadas de **variáveis globais**. As variáveis globais são persistidas na memória durante toda a execução do programa. 

#### Qualificadores de Acesso

==------------------Editando aqui-----------------------==

### Vetores

Vetores (ou arrays) são variáveis que armazenam múltiplos valores – de um mesmo tipo – que são acessados com um único identificador e um índice. Os dados armazenados em um vetor são colocados em endereços sequênciais na memória, com o endereço mais baixo correspondendo ao primeiro índice. Ao definirmos um vetor, podemos definir manualmente seu tamanho – i.e., o número de elementos que ele poderá armazenar – ou deixar que o compilador infira o tamanho com base no número de elementos dutante a declaração.

```c
int arr1[5];
int arr2[] = { 10, 20, 30, 40, 50 };

// Ambos vetores possuem tamanho 5
```

Os arrays são indexados a partir da posição `0`. Assim, o último elemento de um vetor com $n$ elementos, é acessado pelo índice $n - 1$.

```c
float arr[5] = { 1.0, 2.0, 3.0, 4.0, 5.0 };

arr[2] = 3.5;
// Agora arr é armazena os valores { 1.0, 2.0, 3.5, 4.0, 5.0 }
```

Diferente de outras linguagens, C não faz uma verificação de limites para os arrays, cabendo ao programador garantir que o programa não tente acessar algum índice inexistente.

#### Strings

Em C, strings são um tipo específico de vetor: uma cadeia de caracteres terminada com um caracter nulo `'\0'`. Como o caracter nulo também ocupa espaço na memória, o tamanho de uma string deve levar em conta a presença dele. Para anotarmos uma string, é possível escrever uma lista de caracteres entre aspas duplas – `"`. Neste caso, não é necessário adicionar manualmente o caracter nulo, uma vez que o compilador o infere automaticamente.

```c
char str1[11] = "Olá, Mundo";
char str3[11] = { 'O', 'l', 'á', ',', ' ', 'M', 'u', 'n', 'd', 'o', '\0' };

// Ambas atribuições armazenaram os mesmos valores
```

#### Matrizes

Também chamadas de vetores multidimensionais, as matrizes são bascicamente vetores de vetores. Vetores podem ter qualquer número de dimensões, com o limite máximo sendo uma limitação do compilador.

Para se criar um array de duas dimensões, usamos uma declaração assim:

```c
int matrix[2][3] = { { 1, 2, 3 }, { 4, 5, 6 } };
```

### Operadores

#### Operadores Aritméticos e Relacionais

| Operadores Aritméticos | Nome                                     | Operadores de Comparação | Nome             |
| ---------------------- | ---------------------------------------- | ------------------------ | ---------------- |
| `+`                    | Adição                                   | `==`                     | Igual a          |
| `-`                    | Subtração ou Negação (inversão de sinal) | `!=`                     | Não igual a      |
| `*`                    | Multiplicação                            | `>`                      | Maior que        |
| `/`                    | Divisão                                  | `<`                      | Menor que        |
| `%`                    | Módulo (da divisão)                      | `>=`                     | Maior ou igual a |
| `++`                   | Incremento (somar 1)                     | `<=`                     | Menor ou igual a |
| `--`                   | Decremento (subtrair 1)                  |                          |                  |
#### Operadores bit a bit

| Operador | Nome          | Operação realizada                                     |
| -------- | ------------- | ------------------------------------------------------ |
| `&`      | AND           | Retorna `1` se ambos bits forem `1`                    |
| `\|`     | OR            | Renorna `1` se pelo menos um dos bits for `1`          |
| `^`      | XOR           | Retorna `1` se apenas um dos bits for `1` (diferentes) |
| `~`      | NOT           | Inverte todos os bits (`0` vira `1`, `1` vira `0`)     |
| `<<`     | *Shift Left*  | Move os bits para a esquerda, preenchendo com zeros    |
| `>>`     | *Shift Right* | Move os bits para a direita                            |

#### Operadores de Atribuição

Os operadores aritméticos e os opradores bit a bit (exceto o NOT bit a bit / `~`) podem ser combinados com o operador de atribuição `=` para realizar operações com o próprio valor atual.

| Operador | Exemplo   | Equivalência |
| -------- | --------- | ------------ |
| `=`      | `x = 5`   | `x = 5`      |
| `+=`     | `x += 3`  | `x = x + 3`  |
| `-=`     | `x -= 3`  | `x = x - 3`  |
| `*=`     | `x *= 3`  | `x = x * 3`  |
| `/=`     | `x /= 3`  | `x = x / 3`  |
| `%=`     | `x %= 3`  | `x = x % 3`  |
| `&=`     | `x &= 3`  | `x = x & 3`  |
| `\|=`    | `x \|= 3` | `x = x \| 3` |
| `^=`     | `x ^= 3`  | `x = x ^ 3`  |
| `>>=`    | `x >>= 3` | `x = x >> 3` |
| `<<=`    | `x <<= 3` | `x = x << 3` |
#### Operadores Lógicos

| Operador | Nome |
| -------- | ---- |
| `&&`     | AND  |
| `\|\|`   | OR   |
| `!`      | NOT  |

#### Outros Operadores

| Operador                        | Uso                                                              |
| ------------------------------- | ---------------------------------------------------------------- |
| `()`                            | Chamada de função ou indicação de precedência                    |
| `[]`                            | Indeação de vetores                                              |
| `? :`                           | Operador ternário                                                |
| `,`                             | Encadear expressões, avaliando o operador à esquerda como `void` |
| `->`                            | Acesso a membro via ponteiro                                     |
| `.`                             | Acesso a membro de estrutura ou união                            |
| `&` (Operador de Referência)    | Acesso a endereço da memória                                     |
| `*` (Operador de Desreferência) | Acesso ao valor armazenado num endereço da memória               |
| `(tipo)`                        | Conversão (*casting*) de tipo                                    |
| `sizeof`                        | Renorna o tamanho em bytes de uma variável na memória            |


#### Precedência de Operadores

- `()`,  `[]`, `->` , `.`
- `++`, `--`, `-` (negação), `!`, `~`, `&` (referência), `*` (desreferência), `(tipo)`, `sizeof`
- `*`, `/`, `%`  
- `+`, `-`  
- `<<`, `>>`  
- `<`, `<=`, `>`, `>=`  
- `==`, `!=`  
- `&`  
- `^`  
- `|`  
- `&&`  
- `||`  
- `? :`
- `=`, `+=`, `-=`, `*=` etc
- `,`

---
## Estruturas de Controle

Por se tratar de uma linguagem estruturada, o código-fonte em C pode ser delimitado por blocos lógicos que seguem os seguintes pilares:

- **Sequência**: execução linear dos comandos;
- **Seleção**: desvios condicionais – estruturas de seleção;
- **Iteração**: laços de repetição – estruturas de repetição.

### Estruturas de Condicionais

A estrutura de seleção mais básica de seleção é a estrutra `if / else` que contém as seguintes declarações

| Declaração            | Uso                                                                                                                        |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `if (condition)`      | Especifica um bloco de código para ser executado se uma condição for verdadeira                                            |
| `else`                | Especifíca um bloco de código para ser executado se a condição de um `if` for falsa                                        |
| `else if (condition)` | Especifica um bloco de código para ser executado caso uma nova condição for verdadeira, se uma primeira condição for falsa |

Estas estruturas podem ser aninhadas para a veridicação de múltiplas condições. Uma forma de declração que permite reduzir uma condição `if / else` cujo  é usando o operador ternário:

```c
(condition) ? expressionTrue : expressionFalse;
```
 
Ele verifica uma condição e, se ela for verdadeira, realiza a primeira expressão, se for falsa, realiza a segunda. Uma forma de se simplificar a avalização de diferentes possíveis resultados para uma mesma operação é através da declaração `switch`:

```c
switch (expression) {  
  case x:  
    // code block
    break;  
  case y:  
    // code block
    break;  
  default:  
    // code block
}
```

A expressão é avaliada uma única vez e o valor dela é comparado com cada caso, se houver uma correspondência o bloco de código associado a este caso e os casos seguintes são executados. Para evitar que os blocos dos casos seguintes sejam executados, usa-se a palavra reservada `break` para sair do `switch`. É possível ainda determinar um bloco de código `default` (padrão), que é executado se nenhum dos casos for correspondente ao valor da expressão.

### Estruturas de Repetição

C contém três estruturas de loop: `while`, `do / while` e `for`. O loop `while` avalia uma condição e, enquanto ela for verdadeira executa um bloco de códido:

```c
while (condition) {
	// code block
}
```

O loop `do / while` executa o bloco de código associado a ele uma primeira vez, então avalia uma determinada condição, enquanto ela for verdadeira, ele executa novamente o bloco de código:

```c
do {
	// code block
} while (condition);
```

O loop `for` contém três expressões:
- ele realiza a primeira antes da execução do bloco de código;
- avalia então se a segunda expressão (condição) tem um valor verdadeiro;
- se sim, executa o bloco de código;
- a cada execução, realiza a terceira operação
- e, então, verifica a segunda expressão (condição) e, enquanto ela retornar um valor verdadeiro, ele executa novamente o bloco de código.
```c
for (expression1; expression2; expression3) {
	// code block
}
```
C tem ainda as palavras reservadas `break` e `continue` que, usadas junto com estruturas condicionais, permitem alterar o comportamento de um loop em determinadas condições. A palavra `break` –  assim como no `switch` –  permite sair mais cedo de um loop, interrompendo sua execução. A palavra `continue` permite pular uma iteração de um loop, i.e., ele para a execução do bloco de código – ,no caso de um loop `for` executa a terceira expressão –  e verifica se a condição para a execução do loop ainda é satisteita para  executar novamente o bloco.
### Funções

Como uma linguagem procedural, as sub-rotinas são uma parte importante do desenvolvimento usando C. A função `main` é o ponto de partida de qualquer programa em C, é a partir dela que as demais sub-rotinas são chamadas e executadas.

```c
#include <stdio.h>

int main() {
	// Imprime a frase "Olá, Mundo!" no console
    printf("Olá, Mundo! \n");
	
    return 0;
}
```

As funções são o único tipo de sub-rotina presentes em C. Elas são definidas especificando-se o tipo de dado retornado por elas ou `void` caso não seja retornado nenhum dado. Defini-se também o tipo de dado de cada um dos seus parâmetros e o bloco que será executado quando a função for chamada.

```c
int fibonacci(int n) {
    if (n <= 0) return 0;
    if (n == 1) return 1;
	
    int a = 0, b = 1;
    while (n > 1) {
        int temp = a + b;
        a = b;
        b = temp;
        n--;
    }
    
    return b;
}
```

---
## Ponteiros

Ponteiros são variáveis que contém um endereço de memória. Este endereço, normalmente armazena o valor de outra variável, para a qual o ponteiro "aponta para" (*points to*). Para criarmos um ponteiro, informamos o tipo de dado que o endereço armazenado por ele armazenará, usando a seguinte sintaxe:

```text
tipo *nome;
```

Dentre as operações que podemos realizar com ponteiros tempos as de referenciação (`&`) e desreferenciação (`*`). Elas nos permitem, respectivamente, acessar o endereço da memória de uma variável, e acessar o valor armazenado no endereço armazenado por um ponteiro. Ex:

```c
int num = 20;

// Cria um ponteiro
int *ptr;

// Armazena no ponteiro o endereço da variável num
ptr = &num;

// Modifica o valor da variável num através do ponteiro
*ptr = 23;
```

Os ponteiros nos permitem realizar dois tipos de operações aritméticas com eles: adição e subtração. Ao incrementarmos um ponteiro, ele passa a apontar o próximo elemento de seu tipo base, i.e., é somado ao endereço o número de bytes que aquele tipo ocupa na memória. O comportamento é análogo quando decrementamos um ponteiro. Em C, vetores são na verdade, um ponteiro para o seu primiero elemento.  Assim, a cada vez que incrementamos este ponteiro, acessamos o próximo índice.

```c
float arr[] = { 1.0, 2.5, 6.25 };
float *ptr = arr;

*ptr *= 2.0;
*(ptr + 1) *= 3.0;
*(ptr + 2) *= 4.0;

// arr agora armazena os valores { 2.0, 7.5, 25.0 }
```

A linguagem C nos permite ainda criar ponteiros que apontam para outros ponteiros, também chamados de ponteiros de indireção múltipla. I.e., eles armazenam os endereços de outros ponteiros. Podemos ainda criar ponteiros para funções, que armazenam o endereço entrada de uma função e nos permitem chamá-las. Estes últimos são particularmente úteis quando se quer passar uma função como argumento para outra função

```c
int add(int a, int b){
	return a + b;
}

int main() {
	// Cria o ponteiro para a função add
	int (*ptr)(int, int) = add;
	
	// Chama a funçãoo add usando o ponteiro e armazena o resultado na variável x
	int  x = ptr(3, 5);
	// x agora armazena 8
	
	return 0;
}
```

---
## Tipos Compostos – Estruturas, Uniões, Enumerações e `typedef`

---
## Literais e Macros

---
## Bibliotecas e Arquivos de Cabeçalho

