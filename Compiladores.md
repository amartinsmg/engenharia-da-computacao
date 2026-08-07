
## *Front-End* – *Pipeline* de Análise

Antes de ser compilado (ou interpretado) o **código-fonte**  precisa passar um *pipeline* de análise:

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

Lê o código-fonte caractere a caractere e separa as unidades mínimas com significado – os **_Tokens_**. Este processo é análogo ao de separar as palavras de uma frase em uma linguagem natural e é feito pelo componente chamado ***lexer*** ou ***scanner***.

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

Analisa a AST para garantir que seguem as **regras semânticas** da linguagem – i.e., garantir que tenham um significado lógico no contexto do programa. Dentre as verificações feitas nesta etapa são as de **escopo das variáveis** e a **verificação de tipos**. Comparando às linguagens naturais, é semelhante à verificação de um conjunto de frases formarem um texto lógico e coerente. Após esta análise é que a AST com as anotações semânticas é entregue para ser interpretada ou compilada.
