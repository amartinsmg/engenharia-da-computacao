## Conceitos Básicos

Um **computador** é uma máquina eletrônica capaz de sistematicamente coletar, armazenar, maniplar e fornecer os resultados da manipulação de **dados**. Para processar os dados, o computador conta com um **conjunto de instruções** para produzir resultados completos com o mínimo de intervenção humana.

Um sistema baseado em computador é composto por ***Hardware*** – a parte física do computador – e ***Software*** – a parte lógica, i.e., os programas que gerenciam o comportamento do Hardware.

### Componentes de *Hardware*

Podemos dividi-los em 3 classes principais: CPU (Unidade Central de Processamento), memórias e unidades de entrada e saída.

#### Unidades de Entrada e Saída

As **unidades de entrada** (*input*) são os dispositivos físicos que capturam os dados a serem processados. Estes dados podem ser do tipo texto, imagem, áudio, sinais de um sensor etc. Dentre eles cabe citar: mouse, teclado, *scanner*, microfone, dentre outros.

As **unidades de saída** (*output*) apresentam os resultados finais do processamento dos dados. Podemos citar: monitor, auto-falante, impressoras, *plotters* e outros.

Exitem também os dispositivos que se encaixam em ambas categorias, p.ex., unidades de disco, unidades de leitura e gravação de CD e DVD, telas sensíveis ao toque etc.

#### Memória

Responsável pelo armazenamento dos dados e dos programas (instruções) para processá-los. A memória de um sistema computacional trabalha essencialmente com *bits*. Um *bit* pode assumir os valores de `0` ou `1`. Em termos físicos, componetes eletrônicos baseados em CMOS interpretam tensão entre 0 e 1/3 como valor 0, e de 2/3 a 1 como 1. Com isso, é possível reduzir substancialmente a propagação de erros causados por problemas elétricos, por exemplo.

Para representar informações mais complexas, os *bits* são combinados em um conjunto de oito, que recebe a denominação de *byte*. Um conjunto de 2 *bits* consegue armazenar até 2⁸ = 256 valores diferentes. A partir daí, conjuntos cada vez maiores podem ser feitos combinando um número cada vez maior de *bits*/*bytes*:

| Nome     | Símbolo | Valor         |
|----------|---------|---------------|
| byte     | B       | 8 bits (2³)   |
| kilobyte | kB      | 1024 B (2¹⁰)  |
| megabyte | MB      | 1024 kB (2¹⁰) |
| gigabyte | GB      | 1024 MB (2¹⁰) |
| terabyte | TB      | 1024 GB (2¹⁰) |

#### Unidade Central de Processamento

A CPU (*Central Processing Unit*), microprocessador ou processador é o componente que executa as instruções contidas na memória para realizar o processamento dos dados.

> O ciclo básico de execução de qualquer CPU é buscar a primeira instrução da memória, decodificá-la para determinar seus operandos e qual operação executar com os mesmos, executá-la e então buscar, decodificar e executar a instrução subsequente (TANEMBAUM, 2003).

A CPU é composta pelos seguintes componentes:

- **ULA** – Unidade Lógica e Aritmética (*Arithmetic and Logic Unit*): responável por todas as operações aritméticas – soma, subtração, multiplicação etc –, relacionais – se um número é menor, maior ou igual a outro – e lógicas (boolianas) que um computador realiza.
- **UC** – Unidade de Controle (*Control Unit*): responsável por controlar as buscas das instruções e sincronizar a execução.

![Representação da comunicação entre os componentes de hardware de um computador](./imgs/arquitetura-maquina-von-newmann.png)

### Componentes de *Software*

Um programa de computador pode ser definido como uma série de isntruções, em forma inteligível pelo computador, preparada para obter certos resultados. Um programa individualmente pode ser considerado um *software*, porém esse termo também pode ser empregado para a designação de um grupo ou mesmo todo o conjunto dos programas de um computador.

#### *Software* básico

São *software* destinados à operação do computador, i.e., são eles que gerenciam os recursos do *hardware* e permitirem que outros programas possam ser executados.

Dentre eles cabe destacar:

- **Sistema Operacional** – SO: *software* principal que gerencia todo o funcionamento do computador. Dentre suas funções, cabe destacar:
	- Gerenciamento da memória
	- Controle dos processos
	- Controle de *input* e *outpput*
	- Acesso a arquivos
	- Segurança dos dados
	- Interpretação de comandos
- ***Drivers* de dispositivos** – *Device divers*: responsáveis por intermediar a comunicação entre o SO e um componente de hardware, como adaptadores de vídeo, placas de rede, impressoras etc.

#### *Software* aplicativo

Projetados para executar tarefas específicas para o usuário final. Dependem do *software* básico para seu funcionamento.

Podemos citar:

- Navegadores de internet
- Editores de texto
- Planilhas
- Editores de imagem
- Modeladores 3D
- Programas de CAD
- Gerenciadores de Banco de Dados
- E muitos outros...

![Representação da estrutura de um sistema computacional](./imgs/system-structure.jpg)

### Níveis de Programação

Há três diferentes **níveis de abstração** na programação de computadores: linguagem de máquina, linguagem de montagem, linguagem de alto nível. Quanto mais subimos o nível de abstração, mais a linguagem se torna próxima à da lógica humana e mais afastada dos detalhes físicos do hardware.

#### Linguagem de máquina

É a linguagem nativa do computador, formada por instruções em código binárias embutidas na própria arquitetura. Por ser tão dependente da arquitetura do computador, ela apresenta baixa portabilidade, com um código em linguagem de máquina escrito para determinada arquitetura só podendo ser usado em computadores que compartilham a mesma arquitetura.

#### Linguagem de montagem (_Assembly_)

Utiliza representações mnemônicas (palavras curtas, normalmente em inglês) para representar instruções binárias. Cada instrução em _Assembly_ corresponde a uma instrução em linguagem de máquina, sendo por isso também dependente da arquitetura do computador. Contudo, como a máquina não executa diretamente o _Assembly_ é necessário um _software_ chamado de **_Assembler_** (montador) que traduz este código para instruções de máquina.

#### Linguagens de alto nível (_High Level Languages_ - HLL)

São as linguagens que os programadores utilizam no dia a dia, como C, Java e Python. São muito mais próximas da linguagem e da lógica humana e possui termos em inglês estruturados (como  `if`, `while`, `function`). Precisam passar por um processo de tradução feito por **compiladores** ou **interpretadores**  que transformam o código escrito em HLL em linguagem de máquina (passando ou não pelo _Assembly_ no meio do caminho). Por não serem dependentes de arquitetura, são altamente portáveis, podendo ser executados em computadores _desktop_, dispositivos móveis e até mesmo em sistemas embarcados.

![Representação dos níveis de abstração da programação](./imgs/niveis-de-abstracao.webp)

---

## Surgimento e Evolução dos Computadores

Os primeiros dispositivos adotados pelo ser humano com intuito de trabalhar com informações era puramente mecânicos. Antes do advento da eletricidade, apenas engrenagens e outros dispositivos mecânicos era conhecidos, e sua produção contudo era demasiado complexa e cara.

### Máquina de Anticítera

Um computador analógico datado de 87 a.C. capaz de prever eventos astronômicos de forma razoavelmente precisa. Era composto de 37 engrenagens de bronze e foi recuperado em 1901 de um naugráfio próximo à costa da ilha grega de Anticítera

### Máquina Analítica

Conceito elaborado pelo matemático britânico Charles Babbage, entre 1834 e 1837, a partir de um projeto anterior que ele mesmo havia idealizado – a Máquina Diferencial. É considerado o primeiro projeto conceitual de um **computador de uso geral**. Foi desenvolvido para reolve qualquer tipo de problema matemático e executar operações lógicas complexas.

O projeto incorporava uma unidade lógica aritmética, memória interna e controle de fluxo, e introduzia a programação através de cartões perfurados. Embora não tenha chegado a ser construído, sua descrição ganhou muita notoriedade na época, com a versão inglesa sendo extensivamente anotada pela matemática Ada Lovelace. A partir dela, Ada desenvolveu o **primeiro algoritimo**, um método de cálculo de números de Bernoulli.

### Máquina de Turing

Desenvolvida durante a Segunda Guerra Mundial – no ano de 1940 –, a "Bombe" foi um dispositivo eletromecânico desenvolvido por Alan Turing, utilizado com o objetivo de decodificar as mensagens criptografadas do exército alemão. O dispositivo testava bilhões de configurações diariamente para descobrir a chave de segurança das mensagens.

### ENIAC

O ENIAC (_Electronic Numerical Integrator Computer_) foi desenvolvido entre 1943 e 1945 tinha como objetivo o cálculo rápido de trajetórias balisticas com parte do esforço de guerra dos aliados. Ele era composto por 18,000 **vávulas termiônicas** (tubos de vácuo) e consumia cerca de 160 kW. Tinha poder de processamento para realizar 5,000 adições, 357 multiplicações e 38 divisões por segundo. Sua programação contudo era feita via hardware através do rearranjamento de interruptores e conexões de cabos.

### IAS ou Máquina de von Newmann

Contruído pelo Instituto de Estudos Avançados de Princeton (IAS), com projeto e supervisão do matmático John von Newmann, entrou em operação em 1952.  É conhecido por ser um dos primeiros computadores com o conceito de "programa armazenado", no qual as intruções e os dados dividem a mesma memória. A chamada "Máquina de von Newmann" é o modelo teórico que serve como base para o projeto de praticamente todos os computadores atuais.

### Transistores

Os computadores baseados em válvulas termiônicas tinham três desvantagens principais: a baixa confiabilidade – causada por falhas nos contatos ou mesmo queima das válvulas –, alto custo energético e grande volume ocupado. Estes problemas foram resolvidos com a invenção e adoção do **transistor** durante a década de 1950.

Os computadores transistorados trouxeram algumas novdades, dentre as quais os registradores de índices para controle de _loops_ e as unidadas de ponto flutuante (para cálculos de números fracionais). Contudo, eram demasiadamente caros, sendo possuídos apenas por setores governamentais e universidades.

### Circuitos Integrados (CI)

Os **circuitos integrados** (CI), chamados popularmente de _chips_, correspondem ao encapsulamento de diversos transistores numa única pastilha de silício. Foram introduzidos no final da década de 60 e permitiram uma redução ainda maior do tamanho e do gasto energético dos computadores. Com isso se tornaram compactos o suficiente para as empresas de médio porte,.

### Microprocessadores

Em novembro de 1971, a Intel lançou o 4004, o **primeiro microprocessador comercial do mundo**. Ele contava com 2,300 transistores, sendo capaz de executar entre 46,300 e 92,600 intruções por segundo. Isso marcou a integração de toda a CPU num único chip de silício e perimitu o surgimento dos **computadores pessoais** (PCs) usados atualmente.

---

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

## Unidade Central de Processamento (CPU)



---
## Dispositivos de Entrada/ Saída (E/S)


> Os dispositivos de E/S (Entrada e Saída) são constituídos, geralmente, de duas partes: o controlador e o dispositivo propriamente dito. O controlador é um chip ou um conjunto de chips que controla fisicamente o dispositivo; ele recebe comandos do sistema operacional (software), por exemplo, para ler dados dos dispositivos e para enviá-los (TANEMBAUM, 2003).