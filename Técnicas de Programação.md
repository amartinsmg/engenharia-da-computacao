## Linguagens de Programação

As **linguagens de programação** são projetadas com um conjunto de **regras sintáticas e semânticas** para permitirem que *software* seja escrito de uma maneira legível para seres humanos (*human readble*).

Um leque bem grande dentro das linguagens de programação é o das **linguagens de alto-nível** (HLL  – *High-Level Programming Languages*) que trazem uma maior abstração das particularidades do *hardware* que as linguagens de baixo nível (*low-level*). Normalmente elas usam elementos da linguagem natural e permitem automatizar áreas mais complexas dos sistemas (como o gerenciamento de memória), além de permitirem uma maior portabilidade.

> Exemplos: C, C++, Fortran, Java, Python, Rust, Perl, JavaScript

Contudo, como os sistemas computacionais não conseguem compreender diretamente estas linguagens, elas precisam passar por algum processo de conversão  – tradução  – para a **linguagem de máquina** (linguagem binária). Com isto, as HLL se dividem em compiladas e interpretadas.

### *Pipeline* de Análise

Antes de ser compilado ou interpretado, o texto escrito numa determinada HLL  – o chamado **código-fonte**  – precisa passar um *pipeline*:

```text
Texto Bruto (Código-Fonte)
    ↓
[ 1. Análise Léxica ] ─── (Gera Tokens)
	↓
[ 2. Análise Sintática ] ─── (Monta a Árvore Sintática / AST)
	↓
[ 3. Análise Semântica ] ─── (Valida Significados e Tipos)
	↓
Restante da conversão
```

#### Análise Léxica (*Lexing*)

Lê o código-fonte caractere a caractere e separa as unidades mínimas com singnificado – os **_Tokens_**. Este processo é análogo ao de separar as palavras de uma frase em uma linguagem natural e é feito pelo componente chamado ***lexer*** ou ***scanner***.

```text
Exemplo:

- Entrada: int total = preco + 10;

- Saída (Tokens):
    
    1. [Palavra-chave: int]
        
    2. [Identificador: total]
        
    3. [Operador: =]
        
    4. [Identificador: preco]
        
    5. [Operador: +]
        
    6. [Número Inteiro: 10]
        
    7. [Ponto-e-vírgula: ;]
```


Nesta fase também são removidos coisas irrelevantes para o computador como espaços em branco desnecessários e comentários.

#### Análise Sintática (*Parsing*)

Analisa a lista de _tokens_ extraída pelo *lexer* e verifica se ela segue as **regras sintáticas** da linguagem  – e.g., se os parênteses abertos são fechados ou se o valor a ser atribuído a uma variável está à esquerda do operador de atribuição. É um processo análogo ao de verificar se as palavras que constituem uma frase permitem transmitir um significado compreensível numa linguagem natural – uma frase coesa. Ele é feito pelo **_parser_** que retorna a chamada **Árvore Sintática Abstrata** (AST  – *Abstract Syntax Tree*).

```text
Exemplo:

- Entrada: [Identificador: preco] [Operador: +] [Número Inteiro: 10]

- Saída (AST):
  
				  Operador (+)
				 /            \
		   Identificador    Número
		       (preco)        (10)
```

#### Análise Semântica

Analisa a AST para garantir que seguem as **regras semânticas** da linguagem – i.e., garantir que tenham um singnificado lógico no contexto do programa. Dentre as verificações feitas nesta etapa são as de **escopo das variáveis** e a **verificação de tipos**. Comparando às linguagens naturais, é semelhante à verificação de um conjunto de frases formarem um texto lógico e coerente. Após esta análise é que a AST com as anotações semânticas é entregue para ser interpretada ou compilada.

### Linguagens Interpretadas

São linguagens cujo resultado do *pipeline* de análise é entrgue a um programa chamado **interpretador** que processa os blocos de código – linha a linha – **durante a execução**. Como o código-fonte precisa obrigatoriamnete de um **ambiente de execução** (*runtime environment*), isso acaba resultando num maior consumo de recursos durante a execução, porém o torna bastante portável.

> São exemplos de linguagens interpretadas: Python, Perl,  PHP, Rust e JavaScript
### Linguagens Compiladas

Nestas linguagens, o resultado do *pipeline* de análise é passado para um programa chamado **compilador** que o traduz no chamado **código-objeto** – um programa em linguagem de máquina – **antes da execução** (*ahead-of-time*). Este código-objeto pode ser transformado num arquivo executável (que pode ser executado diretamente pelo sistema operacional) ou num arquivo de biblioteca (*library*).

> São exemplos de linguagens compiladas: C, C++, Fortran, Rust, Go e Swift

Como muitas vezes o resultado da compilação pode ser executado diretamente pelo SO, sem a necessidade de um programa intermediário, sua execução tende a ser mais rápida que a de um código fonte interpretado.  Mais ainda, compilador analisa todo o programa antes dele ser executado, ele consegue fazer uma série de **otimizações**, que melhoram ainda mais o desempenho durante a execução.

Contudo, estas linguagens tendem a ser menos portáveis, pois uma arquitetura de hardware ou um sistema operacional diferente, tendem a necessitar de um novo código objeto. Para melhorar sua portabilidade, algumas linguagens como Java, C# e VB.NET não são compiladas para código objeto mas para um **_portable code_** (*p-code* – código portátil) que é interpretado numa **máquina virtual** que faz a execução. Este  *p-code* "conversa" com o conjunto de instruções – consideravelmente compacto – de um processador hipotético/virtual. Como estes conjuntos de instruções  têm normalmente *opcodes* de 1 *byte*, são chamados também de **_bytecode_**.

#### Compilação *Just-in-time* (JIT)

A compilação JIT é uma tecnologia que permite unir a portabilidade e flexibilidade das linguagens interpretadas com o desempenho das linguagens compiladas. O motor JIT compila blocos do código-fonte ou *bytecode* para **código de máquina** nativo **durante a execução** do programa.

O programa começa rodando num interpretador, porém, o motor JIT o monitora em tempo de execução identificando os chamados **_Hotspots_** – trechos de código usados com frequência. A partir de um certo limite, o compilador JIT roda uma ação em segundo plano (*background thread*) que compila aquele trecho de código diretamente para código de máquina nativo da CPU.

>São exemplos de compiladores JIT a JVM (Java Virtual Machine) – que executa *bytecode* Java – e Engine V8, presente no Chrome e no Node.js – que executa JavaScript.

---
## Sistema de Tipos