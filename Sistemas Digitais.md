## Matemática Computacional e Representação de Dados

No nosso mundo, toda informação pode assumir qualquer valor compreendido entre  - ∞ e + ∞, muitas vezes também com infinitos valores intermediários, isto é o que chamamos de valores **analógicos**. Computadores, no entanto, lidam apenas com informações **digitais** – que são por definição discretas, i.e., os dados só podem assumir os valores contidos num conjunto finito. Toda informação manipulada por um computador deve ser reperesentada por ***bits***, que podem assumir os valores `0` e `1`, basicamente, ligado ou desligado.

### Sistemas de Numeração

Os sistemas numéricos são sistemas de notação que nos permitem representar quantidades abstratas denominadas **números**. No nosso dia a dia, normalmente usamos o **sistema decimal**, composto por 10 algarismos (de 0 a 9), porém os computadores trabalham com o **sistema binário** – que usa apenas os dígitos 0 e 1.

#### Sistema Decimal

É um sistema posicional – no qual cada algarismo tem seu valor com base na posição que ocupa no número – no qual cada algarismo é multiplicado por uma potência de **10**. Por exemplo:

- 1822 = 1 \* 10³ + 8 \* 10² + 2 \*10¹ + 2 \* 10⁰ = 1000 + 800 + 20 + 2
- 256 = 2 \* 10² + 5 \*10¹ + 6 \* 10⁰ = 200 + 50 + 6

#### Sistema Binário

Também é um sistema posicional, mas cada algarismo tem seu valor multiplicado por uma potência de 2. Por exemplo, para representar valor decimal 73, temos o valor binário 1001001:

> 1001001 = 1 \* 2⁶ + 0 \* 2⁵ + 0 \* 2⁴ + 1 \* 2³ + 0 \* 2² + 0 \* 2¹ + 1 \* 2⁰ = 64 + 0 + 0 + 8 + 0 + 0+ 1 = 73

Para convertermos de decimal para binário usamos divisões sucessivas por 2. Por exemplo, para converter 55 para binário faz-se:

| Operação | Quociente | Resto |
|----------|-----------|-------|
| 49/2     | 24        | 1     |
| 24/2     | 12        | 0     |
| 12/2     | 6         | 0     |
| 6/2      | 3         | 0     |
| 3/2      | 1         | 1     |
| 1/2      | 0         | 1     |

Quando pegamos os restos a partir do último temos que a representação do número 49 (decimal) equivale 110001 em binário.

#### Sistema Hexadecimal

Embora o sistema binário seja excelente para os computadores, ele se torna demasiado inconveniente para seres humanos, por ser bem mais extensa que a decimal. Já a base decimal apresenta o problema de não ter uma conversão simples para o sistema binário. Para aliar o melhor dos dois sistemas, profissionais da computação frequentemente utilizam o sistema hexadecimal que, como o nome indica, é um sistema posicional de base **16**.
Como o sistema decimal possui apenas 10 dígitos foram adotadas 6 letras para representarem os valores restantes, sendo elas, `A` que equivale a 10, `B` a 11, `C` a 12, `D` a 13, `E` a 14 e `F` a 15.  Por exemplo, a notação hexadecimal 3F5:

> 3F5 = 3 \* 16² + 15 \* 16¹ + 5 \* 16⁰ = 768 + 240 + 5 = 1013

Assim temos que o valor hexadecimal 3F5 equivale ao valor decimal 1013.
Para conversão entre binário e hexadecimal, cada digíto hexadecimal corresponde a 4 dígitos binários, assim, voltando ao exemplo acima:

| 3    | F    | 5    |
|------|------|------|
| 0011 | 1111 | 0101 |

Assim, o valor 3F5 em hexadecimal corresponde ao valor binário 1111110101.
Como o agrupamento mais comum de *bits* usado é o *byte*, que corresponde a 8 *bits*, ele pode ser representado por apenas 2 algarismos hexadecimais.

#### Conjuntos numéricos

Números binários podem representar qualquer número real (R). Contudo, sua representação pode variar em razão do seu tipo. O conunto dos número naturais (N) pode ser representado do omo como visto anteriormente. No entrato ouros conjuntos como o dos numeros inteiros (Z) negativos, racionais (Q) e irracionais (I) requerem representações específicas – que, nas linguagens  de programação, ficam à escolha do programador.

#### Números Negativos

Para representarmos números negativos utiliza-se normalmente a notação conhecida como **"Complemento de 2"**. Neste sistema o bit mais significativo – i.e., aquele mais à esquerda do número – identifica o sinal. O valor `1` indica que o número é negativo, enquanto `0` identifica um valor positivo.

Para representarmos um número negativo qualquer, subtraímos 1 do valor positivo corresponcente e invertemos todos os bits. O processo inverso envolve inverter todos os bits e somar 1.

Por exemplo, para representarmos o número -73 utilizando um único 8 *bits* utilizamos o seguinte método:

| Valor base         | 0 | 1 | 0 | 0 | 1 | 0 | 0 | 1 |
|--------------------|---|---|---|---|---|---|---|---|
| +1                 | 0 | 1 | 0 | 0 | 1 | 0 | 0 | 0 |
| Invertendo os bits | 1 | 0 | 1 | 1 | 0 | 1 | 1 | 1 |

Assim, a notação de -73 usando 8 *bits* é 10110111.

Nas linguagens de programação atuais, o mais comum é utilizarmos 32 ou 64 _bits_ para a representação de inteiros. É comum também termos a possibilidade de decidirmos como o valor do _bit_ mais significativo é interpretado, podendo usá-lo também para representar a magnitude do número. No caso do uso do _bit_ mais significativo para a representação do sinal temos um número **_signed_**, caso contrário, dizemos que é um número **_unsigned_**.

Estes são os limites de representação:

| Representação          | Extensão dos valores (base 2) | Extensão dos valores (base 10)                         |
| ---------------------- | ----------------------------- | ------------------------------------------------------ |
| **32 _bits unsigned_** | de 0 a 2³² - 1                | 0 a 4,294,967,295                                      |
| **32 _bits signed_**   | de -2³¹ a 2³¹ - 1             | -2147483648 a 2147483647                               |
| **64 _bits unsigned_** | de 0 a 2⁶⁴ - 1                | 0 a 18,446,744,073,709,551,615                         |
| **64 _bits signed_**   | de -2⁶³ a 2⁶³ - 1             | -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807 |

#### Números fracionários e dízimas

A forma mais simples de representarmos número fracionários é através de um número fixo de dígitos após a vírgula, i.e., fixamos um número de *bits* para representar a parte inteira e um número de *bits* para a parte fracionária. Assim, cada bit "à direita da vírgula" passa a representar uma potência negativa de 2 (2⁻¹, 2⁻², 2⁻³...).  Estes são os chamados **números fracionários de ponto fixo**.

Contudo, é comum precisarmos utilizar números onde a vírgula pode se deslocar, de forma a permitir a representação de mais dígitos significativos. Para isso utilizamos **notação científica**, representando números fracionários em duas partes: **mantissa** (os dígitos significativos do número) e **expoente**. Tanto a mantissa quanto o expoente podem ser positivos ou negativos, no caso dos números negativos adota-se a notação de complemento de 2. Nesse caso, a **precisão** é dada pela quantidade de bits para a representação da mantissa, já a faixa de números que pode ser representada é dada pelo número de bits do expoente.

Este tipo de representação permite que a vírgula "flutue" para se ajustar a números muito grandes ou muito pequenos sendo por isso chamada de notação de **ponto flutuante**. Pela padronização criada pela IEEE (Instituto de Engenheiros Elétricos e Eletônicos - *Institute of Electrical and Electronics Engineers*) para a representação de números de ponto flutuante com computadores – a IEEE 754 –, temos que o *bit* mais significativo é reservado para a representação do sinal, em seguida vêm os _bits_ destinados à representação do expoente (que deve sempre ser um número inteiro). Os _bits_ menos siginicativos são reservados para a representação da mantissa.

Este é o padrão para a representação de números de ponto flutuante de precisão simples – usando 32 _bits_ – ou dupla precisão – 64 _bits_.

|                  | Precisão simples (32 _bits_) | Dupla Precisão (64 _bits_) |
| ---------------- | ---------------------------- | -------------------------- |
| **Sinal (S)**    | 1 *bit*                      | 1 *bit*                    |
| **Expoente (E)** | 8 _bits_                     | 11 _bits_                  |
| **Mantissa (M)** | 23 _bits_                    | 52 _bits_                  |

[Vídeo explicando a representação de números binários em ponto flutuante.](https://youtu.be/rx3wA1SkrGc?si=QHExlDI0P6xbfeCf)

Um caso curioso ocorre com as **dízimas**, uma vez que números que são dízimas em uma base podem não ser em outra. Um exemplo é o número 0.1 na base decimal, que não pode ser representado em binário com um número finito de dígitos. Isso causa certos erros de aproximação, que quando acumulados podem comprometer a exatidão do resultado final.

Como os algoritmos envolvendo as operações com ponto flutuante (adição, multiplicação, divisão...) podem ser muito complexas existem unidades aritméticas especializadas nestes cáculos, as chamadas Unidades de Ponto Flutuante (_Floating Point Units_). Este tipo de unidade já vem integrada em cada núcleo dos processadores modernos.

#### Tabela ASCII

Os números também podem ser utilizados para representar outros símbolos como letras ou caracteres esperciais. Para isso são utilizados os métodos de codificação, nos quais cada símbolo (caractere) de nossa linguagem é atribuído a um conjunto de _bits_ que o identifica de forma única.

O **Código Padrão Americano para o Intercâmbio de Informação** (_American Standard Code for Information Interchange_ - ASCII) é um destes métodos de codificação que utiliza 7 *bits* para representar 128 sinais: 95 sinais imprimíveis (letras do alfabeto lation, algarísmos arábicos, sinais de pontuação e sinais matemáticos) e 33 sinais de controle.

Esta é a tabela com os caractéres imprimíveis:

| Dec    | Hex |    Char    | Dec    | Hex | Char | Dec     | Hex |  Char   |
| :----- | :-- | :--------: | ------ | :-- | :--: | :------ | :-- | :-----: |
| **32** | 20  | `[Espaço]` | **64** | 40  | `@`  | **96**  | 60  | `` ` `` |
| **33** | 21  |    `!`     | **65** | 41  | `A`  | **97**  | 61  |   `a`   |
| **34** | 22  |    `"`     | **66** | 42  | `B`  | **98**  | 62  |   `b`   |
| **35** | 23  |    `#`     | **67** | 43  | `C`  | **99**  | 63  |   `c`   |
| **36** | 24  |    `$`     | **68** | 44  | `D`  | **100** | 64  |   `d`   |
| **37** | 25  |    `%`     | **69** | 45  | `E`  | **101** | 65  |   `e`   |
| **38** | 26  |    `&`     | **70** | 46  | `F`  | **102** | 66  |   `f`   |
| **39** | 27  |    `'`     | **71** | 47  | `G`  | **103** | 67  |   `g`   |
| **40** | 28  |    `(`     | **72** | 48  | `H`  | **104** | 68  |   `h`   |
| **41** | 29  |    `)`     | **73** | 49  | `I`  | **105** | 69  |   `i`   |
| **42** | 2A  |    `*`     | **74** | 4A  | `J`  | **106** | 6A  |   `j`   |
| **43** | 2B  |    `+`     | **75** | 4B  | `K`  | **107** | 6B  |   `k`   |
| **44** | 2C  |    `,`     | **76** | 4C  | `L`  | **108** | 6C  |   `l`   |
| **45** | 2D  |    `-`     | **77** | 4D  | `M`  | **109** | 6D  |   `m`   |
| **46** | 2E  |    `.`     | **78** | 4E  | `N`  | **110** | 6E  |   `n`   |
| **47** | 2F  |    `/`     | **79** | 4F  | `O`  | **111** | 6F  |   `o`   |
| **48** | 30  |    `0`     | **80** | 50  | `P`  | **112** | 70  |   `p`   |
| **49** | 31  |    `1`     | **81** | 51  | `Q`  | **113** | 71  |   `q`   |
| **50** | 32  |    `2`     | **82** | 52  | `R`  | **114** | 72  |   `r`   |
| **51** | 33  |    `3`     | **83** | 53  | `S`  | **115** | 73  |   `s`   |
| **52** | 34  |    `4`     | **84** | 54  | `T`  | **116** | 74  |   `t`   |
| **53** | 35  |    `5`     | **85** | 55  | `U`  | **117** | 75  |   `u`   |
| **54** | 36  |    `6`     | **86** | 56  | `V`  | **118** | 76  |   `v`   |
| **55** | 37  |    `7`     | **87** | 57  | `W`  | **119** | 77  |   `w`   |
| **56** | 38  |    `8`     | **88** | 58  | `X`  | **120** | 78  |   `x`   |
| **57** | 39  |    `9`     | **89** | 59  | `Y`  | **121** | 79  |   `y`   |
| **58** | 3A  |    `:`     | **90** | 5A  | `Z`  | **122** | 7A  |   `z`   |
| **59** | 3B  |    `;`     | **91** | 5B  | `[`  | **123** | 7B  |   `{`   |
| **60** | 3C  |    `<`     | **92** | 5C  | `\`  | **124** | 7C  |  `\|`   |
| **61** | 3D  |    `=`     | **93** | 5D  | `]`  | **125** | 7D  |   `}`   |
| **62** | 3E  |    `>`     | **94** | 5E  | `^`  | **126** | 7E  |   `~`   |
| **63** | 3F  |    `?`     | **95** | 5F  | `_`  |         |     |         |

---


