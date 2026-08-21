 
## Linguagem C

É uma linguagem de alto nível compilada de propósito-geral, estruturada, imperativa e procedural, criada em 1972 por Dennis Ritchie na AT&T Belll Labs para desenvolvimento do sistema operacional Unix. Atualmente continua sendo usada para o desenvolvimento de sistemas operacionais (especialmente *kernels*), *drivers* de dispositivo, compiladores e softwares aplicativos, sendo compativel com quase todas as arquiteturas computacionais.

É uma das linguagens de programação mais populares no mundo do desenvolvimento de software, tendo influenciado dezenas de outras linguagens (como C++, Java, C#, JavaScript, PHP, Python e muitas outras) e estando presente desde de supercomputadores e computadores domésticos a microcontroladores e sistemas embarcados.

Por se tratar de uma linguagem estruturada, o código-fonte em C pode ser delimitado por blocos lógicos que seguem os seguintes pilares:

- **Sequência**: execução linear dos comandos;
- **Seleção**: desvios condicionais – estruturas de seleção;
- **Iteração**: laços de repetição – estruturas de repetição.

Cada comando é delimitado por ponto-e-vírgula (`;`), e cada bloco, por sua vez,  é delimitado por um par de chaves: `{ }`. Isso facilita o agrupamento lógico e a organização visual do código, além de ajudar a delimitar o escopo das variáveis. Variáveis criadas dentro de um bloco só podem ser acessadas no seu interior.

Como uma linguagem procedural, as sub-rotinas são uma parte importante do desenvolvimento usando C. A função `main` é o ponto de partida de qualquer programa em C, é a partir dela que as demais sub-rotinas são chamadas e executadas.

```c
#include <stdio.h>

int main() {
	// Imprime a frase "Olá, Mundo!" no console
    printf("Olá, Mundo! \n");
	
    return 0;
}
```

Linhas inicidas por `#` em C são diretivas para o pré-processador da linguagem, que  conduz alguns processos antes de mandar o código fonte ao compilador. Os comentários são trechos ignorados pelo compilador (muitas vezes eliminados pelo próprio pré-processador) e podem ser usados para explicar o código e se comunicar com outros desenvolvedores. Comentáios de uma única linha começam com `//`, já blocos de comentário são delimitados por `/* ... */`.

### Variáveis e Tipos de Dados

As variáveis em C podem ter seus nomes (identificadores) formados por letras, números e `_` (sublinha), desde que comece por uma letra ou `_`. Certos nomes são reservados pela linguagem e não podem ser usados como identificadores. Por se tratar de uma linguagem com sensibilidade de caso (*case sensitive*), letras maiúsculas e minusculas são tratadas como distintas nos nomes das variáveis e palavras chaves. I.e., uma variavel chamada `operando` é diferente de outra chamada `OPERANDO` ou `Operando`.

O sistema de tipagem de C é considerado fraco, pois permite certas coersões implicitas, especialmente quando se trabalha com ponteiros. Quanto às demais características do sistema de tipo, pode ser classicada como estática, manifesta e nominal.

#### Tipos Primitivos

| **Tipo / Palavra-chave** | **Tamanho Típico** | **O que armazena?**                                                  |
| ------------------------ | ------------------ | -------------------------------------------------------------------- |
| `void`                   | Nenhum             | Indica ausência de valor (retorno de função) ou tipo genérico.       |
| `char`                   | 8 bits             | Números inteiros de -128 a 127 ou um único caractere (tabela ASCII). |
| `int`                    | 32 bits            | Números inteiros assinalados ($\approx$ -2.14B a 2.14B).             |
| `float`                  | 32 bits            | Números de ponto flutuante ($\approx$ 6-7 casas de precisão).        |
| `double`                 | 64 bits            | Ponto flutuante de precisão dupla ($\approx$ 15-17 casas).           |

Em C existem os **modificadores de tipo** que podem ser usados para alterar o signifcado do tipo-base que os sucedem, fazendo com que ele se adapte melhor a diferentes situações. Todos eles podem ser usados com o tipo inteiro e, quando não é especificado um tipo, o compilador infere automaticamente como `int`.

Os modificadores são:

- `signed` – usado para indicar que podem ser armazenados tanto valores positivos quanto negativos. Todos os `int` são `signed` implicitamente. Pode ser usado também com `char`.
- `unsigned` – usado para indicar que só podem ser armazenados valores positivos (dobrando a capacidade de representação da sua magnitude). Também pode ser usado com `char`.
- `short` – usado para indicar que deve ser alocado um espaço menor na memória para este dado. Normalmente usado para representar inteiros de 16 bits.
- `long` – usado para indicar que deve ser alocado um espaço maior na memória para este dado. Pode ser usado também com o tipo `double`.
- `long long` – usado para indicar que deve ser alocado um espaço de pelo menos 64 bits para esta variável.
#### Tipos Derivados

| **Categoria**            | **Sintaxe** | **O que faz?**                                                                                       |
| ------------------------ | ----------- | ---------------------------------------------------------------------------------------------------- |
| **Ponteiro (*Pointer*)** | `*`         | Armazena o **endereço de memória** de outra variável ou função. Base para alocação dinâmica.         |
| **Vetor (*Array*)**      | `[]`        | Coleção contígua na memória de elementos do **mesmo tipo**.                                          |
| **Estrutura (*Struct*)** | `struct`    | Agrupa variáveis de **tipos diferentes** em um único bloco, criando um tipo personalizado.           |
| **União (*Union*)**      | `union`     | Agrupa variáveis, mas **todas dividem o mesmo espaço na memória**. Ocupa o tamanho do maior membro.  |
| **Enumeração (*Enum*)**  | `enum`      | Cria um conjunto de **constantes inteiras com nomes legíveis**, facilitando a leitura do código.     |
| **Apelido de Tipo**      | `typedef`   | Não cria um tipo novo, mas dá um **nome alternativo** a um tipo já existente para encurtar sintaxes. |

### Operadores

#### Operadores Aritméticos e de Comparação

| Operadores Aritméticos | Nome                | Operadores de Comparação | Nome             |
| ---------------------- | ------------------- | ------------------------ | ---------------- |
| `+`                    | Adição              | `==`                     | Igual a          |
| `-`                    | Subtração           | `!=`                     | Não igual a      |
| `*`                    | Multiplicação       | `>`                      | Maior que        |
| `/`                    | Divisão             | `<`                      | Menor que        |
| `%`                    | Módulo (da divisão) | `>=`                     | Maior ou igual a |
| `++`                   | Incremento          | `<=`                     | Menor ou igual a |
| `--`                   | Decremento          |                          |                  |
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
#### Precedência de Operadores

- `()`,  `++(pós)`, `--(pós)`  
- `++(pré)`, `--(pré)`, `- (unário)`, `!`, `~`
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
- `? : (operador ternário)`   
- `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `<<=`, `>>=`, `&=`, `^=`, `|=`,  
- 
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

