 
## Linguagem C

É uma linguagem de alto nível compilada de propósito-geral, estruturada, imperativa e procedural, com um sistema de tipagem fraca, estática, manifesta e nominal. Foi criada em 1972 por Dennis Ritchie na AT&T Belll Labs para desenvolvimento do sistema operacional Unix. Atualmente continua sendo usada para o desenvolvimento de sistemas operacionais (especialmente *kernels*), *drivers* de dispositivo, compiladores e softwares aplicativos, sendo compativel com quase todas as arquiteturas computacionais.

É uma das linguagens de programação mais populares no mundo do desenvolvimento de software, tendo influenciado dezenas de outras linguagens (como C++, Java, JavaScript, PHP, Python e muitas outras) e estando presente desde de supercomputadores e computadores domésticos a microcontroladores e sistemas embarcados.

### Tipos de Dados em C

#### Tipos Primitivos

| **Tipo / Palavra-chave**  | **Tamanho Típico**                                    | **O que armazena?**                                                  |
| ------------------------- | ----------------------------------------------------- | -------------------------------------------------------------------- |
| `void`                    | Nenhum                                                | Indica ausência de valor (retorno de função) ou tipo genérico.       |
| `char`                    | 1 byte                                              | Números inteiros de -128 a 127 ou um único caractere (tabela ASCII). |
| `bool` (em `<stdbool.h>`) | 1 byte                                              | Lógica: verdadeiro (`1`) ou falso (`0`).                             |
| `int`                     | 4 bytes                                             | Números inteiros assinalados ($\approx$ -2.14B a 2.14B).             |
| `long`                    | 4 ou 8 bytes (varia de acordo com a arquitetura/SO) | Números inteiros de 32 ou 64 bits                                  |
| `long long`               | 8 bytes                                             | Números inteiros muito grandes (64 bits).                          |
| `float`                   | 4 bytes                                             | Números de ponto flutuante ($\approx$ 6-7 casas de precisão).        |
| `double`                  | 8 bytes                                             | Ponto flutuante de precisão dupla ($\approx$ 15-17 casas).           |
Adiconar o prefixo `unsigned` antes dos tipos inteieros (inclusive `char`) permite sobrar o limite máximo positivo da variável, mas remove sua capacidade de guardar valores negativos.

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

Os operadores aritméticos e os opradores bit a bit (exceto o NOT bit a bit – `~`) podem ser combinados com o operador de atribuição `=` para realizar operações com o próprio valor atual.

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
### Estruturas de Condicionais e Repetição

#### Estruturas Condicionais

A estrutura de seleção mais básica de seleção é a estrutra `if / else` que contém as seguintes declarações

| Declaração            | Uso                                                                                                                        |
| --------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| `if (condition)`      | Especifica um bloco de código para ser executado se uma condição for verdadeira                                            |
| `else`                | Especifíca um bloco de código para ser executado se a condição de um `if` for falsa                                        |
| `else if (condition)` | Especifica um bloco de código para ser executado caso uma nova condição for verdadeira, se uma primeira condição for falsa |

Estas estruturas podem ser aninhadas para a veridicação de múltiplas condições. Uma forma de expressão que permite reduzir uma condição `if / else` cujo objetivo é definir o valor de uma variável é usado o operador ternário:

```text
variable = (condition) ? expressionTrue : expressionFalse;
```
 
Ele verifica uma condição e, se ela for verdadeira, atribui à variável o primeiro valor que lhe é fornecido, caso não seja, atribui o segundo.