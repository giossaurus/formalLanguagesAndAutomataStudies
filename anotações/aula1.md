# Introdução e Conceitos Básicos
## Sintaxe e semântica

- O que é uma linguagem formal?
	- Desenvolvida em 1950
	- Estuda e desenvolve teorias relacionadas a linguagem natural
	- Inclinou-se para as linguagens artificias (C, Pascal, etc..)
	- Linguagens ordinárias da ciência da computação

- Qual o enfoque maior?
	- O enforque maior foi em aplicações de análise léxica e análise sintática

- Quais exemplos de linguagens formais?
	- Linguagens de programação, linguagens naturais, expressões matemáticas e circuitos digitais

A sintaxe é a parte da gramática que estuda a disposição das palavras na frase e das frases no discurso. Bem como a **relação lógica** das frases **entre si**.

Exemplos corretos: 
	*José bebeu água. Maria acabou a prova. As flores são belas.*

`if (a <10) then`
`A = 45;`

Exemplos incorretos: 
	*Água bebeu José. A prova acabou Maria. As flores é bela (concordância).* 

`then (a < 10) if`
`45 = a;`

Um erro semântico pode alterar completamente o sentido da frase. Primeiro é feito análise léxica, depois a sintática e por fim a semântica. A frase deve ser analisada como um todo para descobrir o significado de uma palavra.

Exemplo:
- Eu caminho todos os dias
- O caminho é longo
- Vou colher flores
- A colher caiu no chão
- Int soma
- Float soma
- Class soma

	*Caminho: ato de andar*
	*Caminho: estrada*
	*Colher: pegar*
	*Colher: objeto*
	*Soma: valor inteiro*
	*Soma: valor real*
	*Soma: tipo abstrato de dados*
	

Paralelo entre sintaxe e semântica:

Na sintaxe, reconhecemos antes da semântica, o tratamento é mais simples e possui construções matemáticas bem definidas e universalmente reconhecidas(Gramáticas de Chomsky). Ela é LIVRE (sem significado associado) e manipula símbolos.

Na semântica, é analisada após a sintática, tem tratamentos mais elaborados e é baseada em interpretações, logo é mais subjetiva. Ela é ASSOCIADA (com uma interpretação do seu significado).

**Vocabulário inicial para a disciplina**
- Quando for dito que um programa está sintaticamente errado:
	- Isso significa que dentro da linguagem formal a frase correta de se dizer é *"o texto escrito não é aceito pela linguagem"*. Exemplo no caso de não compilar o programa.
- Quando for dito que um programa está sintaticamente correto:
	- Isso significa que *"o texto desse programa é aceito pela linguagem"*. Importante lembrar que pode não ser o programa que o programador esperava escrever (*bug*). Logo dizemos que o programa é *sintaticamente válido.*

## Conceitos básicos

- O que é uma **linguagem**?
	- Segundo o dicionário é o uso da palavra articulada ou escrita como meio de expressão ou comunicação entre pessoas.
	- Não é suficientemente preciso para definir modelos matemáticos.

- Para definir **linguagem formal**
	- Precisamos de um alfabeto e uma cadeia de caracteres ou palavras.

- O que é um **alfabeto**?
	- Um alfabeto é um conjunto **finito** de símbolos ou caracteres. Representado pela notação **∑**.
	- Símbolos ou caracteres podem ser entidades abstratas básicas (letras, dígitos). 
	- São alfabetos: {a, b, c} Ø, conjunto vazio
	- Não são alfabetos: **N**, {aa, aaa, aaaa ...}

- O que seria um **alfabeto em linguagem de programação**?
	- Conjunto de todos os símbolos utilizados na linguagem (letras, dígitos, caracteres especiais como "**>**, **<**, **<=**, **/**, etc e **espaços ou brancos**).
	
- O que seria um **alfabeto binário**?
	- Domínio de valores de um bit, podemos usar {a, b} ou {0, 1}. É muito utilizado para simplificar as abordagens estudadas. É o alfabeto dos circuitos binários do computador.

- O que é uma **palavra**?
	- Também chamada de cadeia de caracteres ou sentença. A palavra é uma sequência finita de símbolos justapostos ou caracteres. Representada pela notação **w**.
	- Exemplo, são palavras no alfabeto {a,b}
		- ab, bb, aaaa
		- **ε** ou **λ** (cadeia vazia)
	- Não são palavras do alfabeto {a,b}
		- ab..., aaa..., abc
- Quais os **elementos** de uma **palavra**?
	- Prefixo: é qualquer sequência inicial de símbolos de uma palavra.
	- Sufixo: é qualquer sequência final de símbolos de uma palavra
	- Subpalavra: é qualquer sequência de símbolos contiguos de uma palavra
	- Comprimento (exemplo **|w|**): onde será o número de caracteres de uma palavra.
		- Exemplo de comprimento: 
			**w = abcb** palavra sobre o alfabeto {a,b,c}
				**ε**, a, ab, abc, abcb são prefixos
				**ε**, a, ab, abc, abcb são sufixos
				Todo sufixo e prefixo é uma subpalavra
				**|w|** = 4
				**|ε|** = 0 (o modulo de cadeia vazia é 0)
		- Exemplo de palavra em linguagem de programação
			- Um bloco de programa
			- Uma palavra-chave, if, while, else, then
			- Um programa inteiro

Propriedades de uma **palavra**:
- **Concatenação**
	- Operação binária sobre um conjunto de palavras, associa duas palavras. É a justaposição da primeira com a segunda.
- **Propriedades**
	- Elemento neutro: $ε w = w = w ε$ 
	- Associativa: $v (w t) = (v w) t$
Exemplos:
	$∑ = {a,b}$ um alfabeto. Para $v = baaab$, $**w = bb**$ (consideramos que $v$ e $w$ são palavras para serem concatenadas)
	$vw = baaabbb$ (concatenadas as palavras $v$ e $w$)
	$vε = baaab$ (concatenada a palavra $v$ com conjunto vazio)

- **Concatenação sucessiva**
	$bˆ4 = bbbb$
	$aˆ0 = ε$	
	$aˆ3 bˆ5=aaabbbbb$	

	Se $∑$ é um alfabeto: $∑*$ é um conjunto de todas as palavras possíveis sobre $∑$
	
	$∑+ = ∑* - ε$

- O que é uma **linguagem formal**?
	- É um subconjunto de $∑*$, isto é, um subconjunto de todas as "palavras" possíveis dentro de um alfabeto.
	- A notação para uma linguagem é representada por $L$, para um dicionário $∑$ e para uma palavra $w$.

**Exemplos:**
- Ø e {$ε$} são linguagens sobre qualquer alfabeto.
- $∑*$ e $∑+$ são linguagens sobre qualquer alfabeto.
- Conjunto de palindromes sobre $∑$ = {$a,b$}:
	 {$ε, a, b, aa, aba, bab, aabbaa, ...$}
- Linguagens de programação:
	- Conjunto de todos programas (palavras) da linguagem
	- Conjunto de palavras chave de uma linguagem (*if, while, int, integer..*)

*C++*
```csharp
	{for, if, while, do, int, new...}
```

*Delphi*
```delphi 
{for, if while, do integer, begin, end...}
```

*Java*
```java
{for, if, while, do, int, foreach...}
```

Como podermos notas, cada linguagem tem um conjunto de palavras que aceita ou seja, esse conjunto de palavras aceitas que chamamos de linguagem.

**Exemplo na programação:**
- A palavra "begin" é aceita pela linguagem **C++**?
	- Não, mas é aceita pela linguagem Pascal ou derivadas dela.

- A palavra "how" é aceita pela linguagem **português**?
	- Não, mas é aceita pela linguagem inglês.
	
- A palavra "teste := 2 * x"  é aceita pela linguagem **Java**?
	- Não, mas é aceita por Pascal, Delphi, etc.. Java não aceita os : junto do sinal de = para atribuição.

- O que é uma **gramática**? 
	- É um conjunto finito de regras que quando aplicada sucessivas vezes geram palavras. O conjunto de todas as palavras geradas por uma gramática define a linguagem.
	- A gramática também é usada para definir semântica.
	
- **Definição formal** de uma **gramática**
	- A Gramática de Chomsky, gramática irrestrita ou apenas gramática:
		$G = (V, T, P, S)$
	- Toda gramática é uma [^1]**tupla** de quatro conjuntos, sendo eles o conjunto das variáveis $V$, terminais $T$, regras de produção $P$ e inicial $S$

	- $V$ é o conjunto finito de símbolos, variáveis ou não-terminais.                          
	- $T$ é o conjunto finito de símbolos e terminais.
	- $P$ são as produções.
			$(V∪T)+ → (V∪T)+$, relação finita.
			Par de relação, regra de produção ou só produção.
	- $S$ é o elemento diferente de $V$, variável inicial.
	
[^1]: Tuplas são estruturas de dados que armazenam uma sequência de valores de diferentes tipos. São imutáveis, ou seja, os valores não podem ser alterados. São leves e fáceis de criar e representadas por uma sequência de valores separados por vírgula e entre parênteses

- Representação de uma **regra de produção** na **gramática**
	- $α → β$
		Se $α$ tem mais de uma produção:
		-  $α → β1$
		-  $α → β2$
		-  $α → β3$
		Pode-se abreviar para  $α → β1|β2|β3$

	**Exemplo**: Onde tem $6$ eu posso trocar por $12/2$, sendo $6 → 12/2$. Onde tem uma centena posso trocar para $100$,  sendo $1  centena → 100$. Onde tem azul posso trocar por branco (se determinar a regra de produção), $azul → branco$.

- O que é a **derivação**?
	- É o processo de aplicar as regras de produções. Substituindo uma sub palavra segundo uma regra de produção. Exemplo, para estas regras $α → β1|β2|β3$ podemos substituir $α$ por $β1$, por $β2$ ou por $β3$
	- A derivação inicia-se sempre de $S$
	- Permite gerar as palavras da linguagem
	
	**Exemplo prático de derivação:**
	$G = (V, T, P, S)$

	$V =${$N,D$}
	$T=${$0,1,2,3,4,5,6,7,8,9$}
	$P =${
		$N → D$
		$N → DN$
		$D → 0|1|2|3|4|5|6|7|8|9$
		}
	$S =${$N$}

	Para facilitar vamos numerar as regras de produção sendo:
		$N → D$ (regra 1)
		$N → DN$ (regra 2)
		$D → 0|1|2|3|4|5|6|7|8|9$ ( regra 3)
		
	Vamos agora derivar o número 243 usando essas regras de produção:
	$N → DN$ , aplicando a regra 2
	$DN → 2$  , aplicando a regra 3 para alterar o $D$ que se tornou $2N$
	$2N → 2DN$ , aplicando a regra 2	
	$2DN → 4$ , aplicando a regra 3 para alterar D que se tornou $24N$
	$24N → D$ , aplicando regra 1 e gerando $24D$
	$24D → 3$ , aplicando a regra 3 novamente e gerando $243$
	
	Exercícios extras - Faça as seguintes derivações:
	- 1) 1000
	- 2) 02
	- 3) 5890
	- 4) 3,45
		
	Podemos concluir que a gramática anterior produz a linguagem dos números naturais. Denotamos **LINGUAGEM GERADA** por $G:L(G)$ ou $GERA(G)$. 
	Para que duas linguagens $G1$ e $G2$ sejam iguais ou equivalentes:
	$L(G1)=L(G2)$
	Isto é, o conjunto das palavras aceitas devem ser iguais.

	Convencionaremos que:
	- $A,B,C,S...T$  as letras maiúsculas serão para variáveis.
	- $a,b,c,s...t$  as letras minúsculas serão para terminais.
	- $u, v, w, y, z$  para palavras de símbolos terminais.