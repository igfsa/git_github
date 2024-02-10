## Introdução ##

&xrArr; Markdown é um arquivo que utiliza recursos para renderização de seu conteúdo como HTML. Ao adicionar um arquivo como README.md, o GitHub utiliza deste arquivo para renderizar na página do diretório do arquivo, assim atribuindo descrição direta a página. 

Este documento indica e serve de referência para alguns dos principais recursos, este [link](https://www.markdownguide.org/ "Markdown Guide") é um guia para markdown que possui comandos além dos vistos aqui.

--------------------------

## Parágrafos ##

&xrArr; Para separar parágrafos devem ser utilizados dois enters, assim irá ocorrer a renderização do elemento como um parágrafo. Um enter simples indica quebra de linha, mas não um novo parágrafo.

--------------------------

## Títulos ##

&xrArr; Títulos podem ser marcados utilizando `#`. Por basear no HTML, existem 6 tamanhos de título que podem ser aplicados, com a quantidade de `#` utilizados indicado qual tamanho de título estamos usando. 

# Título 1 #

## Título 2 ##

### Título 3 ###

#### Título 4 ####

##### Título 5 #####

###### Título 6 ######

&xrArr; O título h1 também pode ser aplicado ao inserir o sinal `=` na linha abaixo do título e o título h2 também pode ser aplicado ao inserir o sinal `-` na linha abaixo do título. 

Título 1
=

Título 2
-

--------------------------

## Divisão horizontal ##

&xrArr; Uma divisão horizontal pode ser feita inserindo `---` em uma linha.

--------------------------

## Itálico ##

&xrArr; Inserir textos ém itálico é possível ao inserir a mensagem entre ou asterisco ou underline, um ao início e um ao final. Espaço junto dos caracteres de marcação impede o uso deste recurso.

_Itálico 1_ *Itálico 2*

--------------------------

## Negrito ##

&xrArr; Inserir textos em negrito é possível ao inserir a mensagem entre ou dois asteriscos ou dois underlines, dois ao início e dois ao final. Espaço junto dos caracteres de marcação impede o uso deste recurso.

__Negrito 1__ **Negrito 2**

--------------------------

## Tachado ##

&xrArr; Inserir textos tachados é possível ao inserir a mensagem entre dois tils, dois ao início e dois ao final. 

~~A terra é plana~~

--------------------------

## Subscrito ##

&xrArr; Subscrito pode ser feito inserindo o conteúdo entre `<sub></sub>`.

H<sub>2</sub>O

--------------------------
## Sobrescrito ##

&xrArr; Sobrescrito pode ser feito inserindo o conteúdo entre `<sup></sup>`.

10<sup>7</sup>

__________________________

## Links ##

&xrArr; Links podem ser inseridos utilizando colchetes para identificar o  texto a ser exibido e logo em seguida parênteses com o link de destino. Dentro dos parênteses contendo o link também é possível inserir um texto ao sobrepor o mouse. 

[Meu site](www.riss.com.br "Home de meu site")

Caso a necessidade de um link ou contato seja mais simples, apenas com o link de destino, o conteúdo pode ser inserido entre `< >`

<https://www.riss.com.br>

--------------------------

## Citações ##

&xrArr; Citações podem ser destacadas ao inserir `>` no início das linhas da citação. 

> Este é um exemplo de citação.

--------------------------

## Listas ##

&xrArr; Listas não ordenadas podem ser criadas ao inserir `*` no inicio da linha e para subitens utilizando tabulação. 

* Fiat
  * Uno
    * 1.0
    * 1.4
  * Mobi 
    * 1.0
    * 1.4
* Renault 
  * Sandero 
    * 1.0

&xrArr; Para listas ordenadas ao invés de utilizar o símbolo `*` devem ser utilizados os números.

1. Fiat
   1. Uno
      1. 1.0
      2. 1.4
   2. Mob1
      1. 1.0
      2. 1.4
2. Renault 
   1. Sandero
      1. 1.0
   
&xrArr; Para listas ordenadas automaticamente é necessário apenas inserir `1.` em cada nova linha, ao renderizar o arquivo já ocorre a atualização dos números. 

1. Fiat 
   1. Uno
      1. 1.0
      1. 1.4
   1. Mobi
      1. 1.0
      1. 1.4
1. Renault 
   1. Sandero
      1. 1.0

--------------------------

## Imagens ##

&xrArr; Imagens presentes no diretório podem ser inseridas. É feito de forma semelhante à inserção de links, com necessidade de inserir o símbolo ! antes do primeiro colchete.

![et](media/et.png "et")

&xrArr; Imagens da web também podem ser inseridas da mesma forma.

![gif dev](https://riss.com.br/media/dev.gif "gif dev")

&xrArr; Também pode ser utilizado HTML para inserir imagens em um markdown, porém nem todos renderizadores possuem suporte. Desta forma, é possível alterar o tamanho de exibição da imagem. 

<img src="media/et.png" width="300">

--------------------------

## Tabelas ##

&xrArr; Tabelas também podem ser inseridas, utilizando `|` para delimitar colunas e `-` para dividir cabeçalhos.

Potência | Valor 
---------|-------
10<sup>1</sup>|10
10<sup>2</sup>|100
10<sup>3</sup>|1000
10<sup>4</sup>|10000

Além do alinhamento padrão à esquerda, também pode ser definido como centralizado, inserindo `:` no inicio e no final da linha que indica a coluna desejada, ou à esquerda, inserindo `:` no final da linha que indica a coluna desejada.

Potência | Valor 
:-------:|-------:
10<sup>1</sup>|10
10<sup>2</sup>|100
10<sup>3</sup>|1000
10<sup>4</sup>|10000

--------------------------

## Texto de código ##

&xrArr; É possível inserir texto de código, que será renderizado em um bloco com destaque. Os hyperlinks ou recursos que seriam utilizados para renderização do markdown também são ignorados. Pode ser feito inserindo o código entre &grave; &grave;.

`## Este é um exemplo de texto de código.## Recursos do markdown podem ser digitados aqui porém sem sua renderização, como em **negrito** ou _itálico_.`

&xrArr; Para blocos em várias linhas/parágrafos, o código deve ser inserido entre duas linhas contendo ```.

```
#include <stdio.h>
#include <stdlib.h>

void main() {
    printf("Olá mundo!");
}
```

&xrArr; Ao inserir a linguagem ao lado dos sinais ``` presentes na primeira linha, o texto aparece em cores, respeitando as estruturas da linguagem 

### C ###

```c
#include <stdio.h>
#include <stdlib.h>

void main() {
    printf("Olá mundo!");
}
```

### HTML ###

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Exemplo</title>
    </head>
    <body>
        <center>
            Exemplo de texto.
        </center>
    </body>
</html>
```

--------------------------

## Lista de tarefas ##

&xrArr; É possível criar uma lista de tarefas, onde serão renderizadas caixas de seleção que possuem indicativo de marcação. Para criar a caixa, basta digitar `[ ]`. Para marcar a caixa, basta inserir `x` entre os colchetes

### Tarefas ###

  - [X] ~~Acordar~~   
  - [X] Tomar banho
  - [ ] Tomar café

--------------------------

## Notas de rodapé ##

&xrArr; Notas de rodapé podem ser inseridas colocando entre colchetes o nome da nota no local desejado `[nota]` e o conteúdo sendo indicado em outro local com o nome da nota entre colchetes, dois pontos e o conteúdo da nota `[nota]: conteúdo`. Para notas de múltiplas linhas, a tabulação faz o vínculo. Elementos como blocos de código podem ser inseridos e o conteúdo da nota pode ser inserido em qualquer lugar do código desde que não esteja dentro de outros elementos como tabelas.

Esta é uma nota de rodapé [^1].

[^1]: Este é o conteúdo da nota de rodapé.
    
    Aqui estão várias linhas. 
    
    ```c
    #include <stdio.h>
    #include <stdlib.h>

    void main() {
        printf("Olá mundo!");
    }
    ```

--------------------------

## Referências/variáveis ##

&xrArr; É possível criar referências de links e diretórios dentro do arquivo e utiliza-las como variáveis. Desta forma, ao inserir a referência na renderização é utilizado o conteúdo atribuído a ela, assim evitando de repetir o conteúdo na escrita do material. São configuradas com `[nome]: conteúdo` e chamadas através de `[nome]`

Exemplo com meu [site][site]

Exemplo com uma imagem:

![et][et]


[site]: riss.com.br "Home de meu site"
[et]: media/et.png "et"

--------------------------

## Emojis e símbolos ##

&xrArr; É possível utilizar símbolos HTML através de seus códigos em um arquivo markdown. O símbolo &xrArr; utilizado neste arquivo é um exemplo. Este [link](https://en.wikipedia.org/wiki/List_of_XML_and_HTML_character_entity_references "Lista de referências de caracteres HTML") possui os símbolos HTML.

&xrArr; Também é possível inserir emojis de forma similar aos símbolos HTML. Este [link](https://gist.github.com/rxaviers/7360908 "Lista de emojis") possui emojis para se utilizar em markdown no GitHub. 

:trollface:
:shipit:
