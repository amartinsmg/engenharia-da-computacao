## Linguagens de Programação

As **linguagens de programação** são projetadas com um conjunto de **regras sintáticas e semânticas** para permitirem que *software* seja escrito de uma maneira legível para seres humanos (*human readable*).

Um leque bem grande dentro das linguagens de programação é o das **linguagens de alto-nível** (HLL  – *High-Level Programming Languages*) que trazem uma maior abstração das particularidades do *hardware* que as linguagens de baixo nível (*low-level*). Normalmente elas usam elementos da linguagem natural e permitem automatizar áreas mais complexas dos sistemas (como o gerenciamento de memória), além de permitirem uma maior portabilidade.

> Exemplos: C, C++, Fortran, Java, Python, Rust, Perl, JavaScript

Contudo, como os sistemas computacionais não conseguem compreender diretamente estas linguagens, elas precisam passar por algum processo de conversão  – tradução  – para a **linguagem de máquina** (linguagem binária). Com isto, as HLL se dividem em compiladas e interpretadas.

### Linguagens Interpretadas

São linguagens cujo arquivo de texto escrito pelo programador – chamado de **código-fonte** – é entregue a um programa chamado **interpretador** que processa os blocos de código, linha a linha, **durante a execução**. Como o código-fonte precisa obrigatoriamente de um **ambiente de execução** (*runtime environment*), isso acaba resultando num maior consumo de recursos durante a execução, porém o torna bastante portável.

> São exemplos de linguagens interpretadas: Python, Perl,  PHP, Rust e JavaScript
### Linguagens Compiladas

Nestas linguagens, o resultado do *pipeline* de análise é passado para um programa chamado **compilador** que o traduz num  programa em linguagem de máquina  – chamado **código-objeto** – **antes da execução** (*ahead-of-time*). Este código-objeto pode ser transformado num arquivo executável (que pode ser executado diretamente pelo sistema operacional) ou num arquivo de biblioteca (*library*).

> São exemplos de linguagens compiladas: C, C++, Fortran, Rust, Go e Swift

Como muitas vezes o resultado da compilação pode ser executado diretamente pelo SO, sem a necessidade de um programa intermediário, sua execução tende a ser mais rápida que a de um peograma interpretado.  Mais ainda, como o compilador analisa todo o programa antes dele ser executado, ele consegue fazer uma série de **otimizações**, que melhoram ainda mais o desempenho durante a execução.

Contudo, estas linguagens tendem a ser menos portáveis, pois uma arquitetura de hardware ou um sistema operacional diferente, tendem a necessitar de um novo código objeto. Para melhorar sua portabilidade, algumas linguagens como Java, C# e VB.NET não são compiladas para código objeto mas para um **_portable code_** (*p-code* – código portátil) que é interpretado numa **máquina virtual** que faz a execução. Este  *p-code* "conversa" com o conjunto de instruções – consideravelmente compacto – de um processador hipotético/virtual. Como estes conjuntos de instruções  têm normalmente *opcodes* de 1 *byte*, são chamados também de **_bytecode_**.

#### Compilação *Just-in-time* (JIT)

A compilação JIT é uma tecnologia que permite unir a portabilidade e flexibilidade das linguagens interpretadas com o desempenho das linguagens compiladas. O motor JIT compila blocos do código-fonte ou *bytecode* para **código de máquina** nativo **durante a execução** do programa.

O programa começa rodando num interpretador, porém, o motor JIT o monitora em tempo de execução identificando os chamados **_Hotspots_** – trechos de código usados com frequência. A partir de um certo limite, o compilador JIT roda uma ação em segundo plano (*background thread*) que compila aquele trecho de código diretamente para código de máquina nativo da CPU.

>São exemplos de compiladores JIT a JVM (Java Virtual Machine) – que executa *bytecode* Java – e Engine V8, presente no Chrome e no Node.js – que executa JavaScript.

---
### Sistema de Tipos (*Type System*)

É o conjunto de regras de uma linguagem de programação que nos permite categorizar valores, variáveis e expressões e controlar como serão manipulados e armazenados na memória.

#### Tipos de Dados (*Data Types*)

Um sistema de tipos é baseado nos **tipos de dados**, que representa o conjunto de valores e operações  que podem ser realizadas com estes valores.

##### Tipos Primitivos

São os tipos mais fundamentais fornecidos pela linguagem e suportados, na maioria das vezes, pelo próprio conjunto de instruções da CPU. São eles:

- **Inteiro**: representam números sem parte fracionária. Normalmente podem ter 8, 16, 32 ou 64 *bits* dedicados a sua representação. Podem ser assinados (*signed* – suportando números negativos) ou não assinados (*unsigned*);
- **Ponto Flutuante** (*Floating-point*): representam números reais (podendo ou não conter parte fracionária). Normalmente tem 32 (*single precision*) ou 64 (*double precision*) *bits* de precisão, sendo representados seguindo as normas da IEEE 754 – que define como os *bits* são divididos para representar sinal, expoente e mantissa;
- **Booleanos**: representam valores lógicos – verdadeiro ou falso, *true* ou *false*;
- **Caracteres**: representam símbolos individuais – que podem ser codificados em ASCII, UTF-8, UTF-16 etc – podendo representar sinais gráficos ou de controle (como quebra de linha, tabulação e outros).

##### Tipos Estruturados ou Derivados

São criados a partir da combinação de tipos primitivos:

- **_Arrays_ /  Vetores**: representam uma sequência **contínua** de elementos do **mesmo tipo** na memória;
- ***Strings***: um tipo especial de vetor dedicado a representar uma cadeia de **caracteres**;
- **Ponteiros** (*pointers*): armazenam um valor que "aponta para" um dado armazenado na memória usando seu endereço;
- **Tipos definidos pelo usuário** (*struct*|*enum*|*class*): permitem ao programador combinar tipos de dados primitivos para atender a alguma necessidade específica.

##### Tipo de Dado Abstrato (ADT - *Abstract Data Type*)

Conceito **puramente teórico e abstrato** presente nas HLL mais modernas que define um tipo de dado não pela sua implementação interna (o que ele é), mas pelo seu comportamento (o que ele faz). Em outras palavras o que define um tipo de dado é a interface – i.e., o conjunto das operações – que nos permite interagir com ele.

#### Tipagem

Nas diferentes HLL, uma variável pode ter seu tipo de dado associado diretamente a ela ou não. Chamamos de tipagem **estática** (*static*) quando uma variável é associada a um tipo específico de valores. Por exemplo, uma variável associada ao tipo inteiro só pode armazenar este tipo de dado – como ocorre em C, C++, Rust, Go, Pascal, Java, TypeScript. É muito comum em linguagens compiladas, permitindo que a verificação de tipos seja analisada já durante a fase da análise semântica e permitem um melhor desempenho.

Quando o tipo não está associado diretamente à variável, mas aos próprios valores armazenados por elas, dizemos que a tipagem é **dinâmica** (*dynamic*). Neste caso, a variável é apenas um rótulo e o tipo de dado armazenado por ela pode ser alterado ao longo do programa. São exemplos de linguagens que usam tipagem dinâmica Python, JavaScript, Ruby, Julia e PHP. Este tipo de tipagem é mais comum em linguagens interpretadas e permite uma maior flexibilidade.

Quanto à atribuição do tipo de uma variável, a tipagem pode ser explicita ou inferida. Nas linguagens com tipagem **explícita** (*explicit*) ou *manifest* – como C, Pascal, Java (tradicional) – o programador é obrigado a escrever (explicitamente) o tipo de dado que uma variável irá armazenar. Já na tipagem **inferida** (*inferred*), o próprio compilador ou interpretador deduz (infere) o tipo de dado da variável com base na primeira atribuição. A tipagem *inferred* está presente em linguagens como TypeScript, Java (moderno – `var`), Julia e Rust.

Nas linguagens com tipagem estática, o modo como um compilador ou interpretador precisa verificar se dois tipos são iguais ou compatíveis para realizar determinada operação. Na tipagem nominal (_nominative_) dois tipos são iguais somente se tiverem o mesmo “nome” ou se houver alguma declaração explícita – como acontece em linguagens como Java, C++ e Julia. Já na tipagem estrutural (*structural*), dois tipos são considerados iguais se tiverem a mesma estrutura, i.e., se tiverem o mesmo conteúdo –  está presente em TypeScript, Rust e Go.

Já nas linguagens dinâmicas há a presença do chamado *duck typing*, no qual é empregado o teste do pato (*duck test*) – “se anda como um pato e faz quack como um pato, então é um pato” – para determinar se um dado pode ser usado numa operação específica. São exemplos de linguagens que o usam Python, Ruby, JavaScript. Seu funcionamento é semelhante ao *structural typing*, com a diferença de que a verificação não é feita no momento da compilação, mas durante a execução, e de que não é verificado o tipo do dado, apenas sua compatibilidade com a operação.

#### Segurança de Tipos (*Type Safety*)

Pode ser definida como o grau que uma linguagem desencoraja ou previne **erros de tipos** (*type erros*), garantindo que um programa não tentará realizar operações inválidas sobre os dados – como tentar somar uma *string* e um inteiro. Uma linguagem com maior segurança de tipos – também chamada de **fortemente tipada** (*strong typing*)  – não permite que operações com dados incompatíveis sejam realizadas, lançando uma exceção na compilação – como é o caso do Java, Rust, Go e TypeScript – ou execução do código – Python, Rust e Julia. 

Em linguagens consideradas  **fracamente tipadas** – também chamadas de *type-unsafe* – tentam "adivinhar" o resultado esperado e realizam conversões de tipo automáticas, como o JavaScript e o PHP. Outras linguagens como C/C++ permitem manipulações de endereços brutos de memória (ponteiros), permitindo fazer *casting* (coerção) sem nenhuma verificação de tipos. Quanto maior a tipagem de uma linguagem, menor a chance de gerar resultados imprevisíveis e quebrar o programa.

Algumas linguagens como Rust e Go tem uma segurança de tipos ainda maior a nível de compilador. Diferente de linguagens como Java e Python que promovem uma conversão implícita de tipos numéricos – or exemplo, permitindo que um número inteiro e um de ponto flutuante sejam somados, resultando num número de ponto flutuante –, estas linguagens obrigam que estas conversões sem feitas de maneira explícita, ou a compilação é abortada na análise semântica. Em Rust a segurança é ainda mais extrema, impedindo implícitas até entre inteiros de tamanhos diferentes (um inteiro de 32-*bits* e um de 64-*bits* não podem ser usados na mesma operação sem uma conversão explícita).

### Propósitos de Uso e Paradigmas de Programação

Quanto ao propósito, existem basicamente dois tipos de linguagens de programação:

- **Linguagens de Propósito General** (GPL – *general-purpose languages*) – capazes de serem usadas para desenvolver *software* em diferentes domínios de aplicação. Sendo caracterizadas por serem **_Turing complete_** , i.e., podendo computar qualquer algoritmo teoricamente possível. São exemplos: C/C++, Java, Python, JavaScript, Rust, Go, Julia, dentre outros.
- **Linguagens de Domínio Específico** (DSL – *domain-specific language*) – feitas para resolver algum problema num domínio particular. São exemplos: SQL HTML, CSS, Expressões Regulares (Regex) e LaTex. Não são *Turing complete* e são consideradas puramente declarativas – indicando apenas o que deve ser feito.

Já quanto ao paradigma, as linguagens de programação se dividem em dois ramos principais:

```text
                        Paradigmas de Programação
                                   │
         ┌─────────────────────────┴─────────────────────────┐
         ▼                                                   ▼
 PARADIGMAS IMPERATIVOS                               PARADIGMAS DECLARATIVOS
 ("COMO" resolver o problema)                         ("O QUE" deve ser resolvido)
 │                                                    │
 ├─ Estruturado                                       ├─ Funcional (ex: Haskell)
 ├─ Procedural (ex: C, Pascal, Fortran clássico)      ├─ Lógico (ex: Prolog)
 └─ Orientado a Objetos (POO | ex: Java)              └─ DSLs (ex: SQL, HTML, CSS)
```

#### Paradigmas Imperativos

Focam no modo como o problema deve ser resolvido, através de comandos que manipulam estados (variáveis, memória) de um processo. Ou seja, ele descreve  – passo a passo – o controle de fluxo (*control flow*) do programa.  São subtipos:
- **Estruturado**: segue os princípios do paradigma imperativo, mas organiza o código em uma estrutura de blocos para organizar o *control flow*. Ele usa sequência, seleção (`if` – `else`) e interação (*loops*) para eliminar saltos randômicos ao longo do programa (`goto`).
- **Procedural**: segue os princípios do paradigma estruturado, organizando o código em procedimentos (*procedures*), também chamados de funções ou sub-rotinas, capazes de chamar uns aos outros e serem reutilizados.
- **Orientado a Objetos**: deriva do procedural e se baseia em objetos que agrupam dados (atributos) e procedimentos (métodos). São seus pilares: encapsulamento, herança, polimorfismo e abstração.

#### Paradigmas Declarativos

Estas linguagens focam em descrever a lógica do programa sem descreverem o *control flow*. Trata-se da abstração de um programa além da ordem de execução, descrevendo o resultado esperado ou a lógica da solução de um problema.
- **Funcional**: deriva do declarativo aplicando o conceito de função matemática, sem alterações de estados e sem efeitos colaterais (uma função pura retorna o mesmo resultado para os mesmos argumentos). Funções aqui são consideradas "cidadãos de primeira classe", podendo ser passadas como argumento para outras funções e/ou retornadas por elas.
- **Lógica**: também deriva do paradigma declarativo aplicando a lógica matemática, através de fatos e regras de inferência lógica.

#### Linguagens Multiparadigma  e Paradigmas Transversais

As HLL que temos hoje são, em sua maioria, multiparadigma, suportando diversos paradigmas – como Python que é imperativa, orientada a objetos e funcional. Com isso, temos também outros paradigmas, chamados de transversais, cujas características podem se aplicar a qualquer paradigma:
- **Concorrente / Paralela**: foca na execução de múltiplos fluxos de execução (*threads* ou processos) que ocorrem de maneira simultânea ou intercalada (ex: C/C++ com a lib OpenMP, Java a partir da versão 8).
- **Orientada a Eventos** (*Event-Driven*): o *control flow* é determinado por **eventos externos** e *callbacks* (ex: JavaScript esperando uma requisição HTTP, uma interface gráfica).
- **Modular**: divide um sistema grande em partes menores, independentes e reutilizáveis chamadas de **módulos** – presente em praticamente todas as linguagens hoje em dia.
