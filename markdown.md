## Introdução ##

=> Markdown é um arquivo que utiliza recursos para renderização de seu conteúdo como HTML. Ao adicionar um arquivo como README.md, o GitHub utiliza deste arquivo para renderizar na página do diretório do arquivo, assim atribuindo descrição direta a página. 

Este documento indica e serve de referência para alguns dos principais recursos, este [link](https://www.markdownguide.org/cheat-sheet/ "Markdown Guide") é um guia para markdown que possui comandos além dos vistos aqui.

--------------------------

## Parágrafos ##

=> Para separar parágrafos devem ser utilizados dois enters, assim irá ocorrer a renderização do elemento como um parágrafo. Um enter simples indica quebra de linha, mas não um novo parágrafo.

--------------------------

## Títulos ##

=> Títulos podem ser marcados utilizando '#'. Por basear no HTML, existem 6 tamanhos de título que podem ser aplicados, com a quantidade de '#' utilizados indicado qual tamanho de título estamos usando. 

# Título 1 #

## Título 2 ##

### Título 3 ###

#### Título 4 ####

##### Título 5 #####

###### Título 6 ######

=> O título h1 também pode ser aplicado ao inserir o sinal '=' na linha abaixo do título e o título h2 também pode ser aplicado ao inserir o sinal '-' na linha abaixo do título. 

Título 1
=

Título 2
-

--------------------------

## Divisão horizontal ##

Uma divisão horizontal pode ser feita inserindo '---' em uma linha.

--------------------------

## Itálico ##

=> Inserir textos ém itálico é possível ao inserir a mensagem entre ou asterisco ou underline, um ao início e um ao final. Espaço junto dos caracteres de marcação impede o uso deste recurso.

_Itálico 1_ *Itálico 2*

--------------------------

## Negrito ##

=> Inserir textos em negrito é possível ao inserir a mensagem entre ou dois asteriscos ou dois underlines, dois ao início e dois ao final. Espaço junto dos caracteres de marcação impede o uso deste recurso.

__Negrito 1__ **Negrito 2**

--------------------------

## Tachado ##

=> Inserir textos tachados é possível ao inserir a mensagem entre dois tils, dois ao início e dois ao final. 

~~A terra é plana~~

--------------------------

## Subscrito ##

=> Subscrito pode ser feito inserindo o conteúdo entre `<sub></sub>`.

H<sub>2</sub>O

--------------------------
## Sobrescrito ##

=> Sobrescrito pode ser feito inserindo o conteúdo entre `<sup></sup>`.

10<sup>7</sup>

__________________________

## Links ##

=> Links podem ser inseridos utilizando colchetes para identificar o  texto a ser exibido e logo em seguida parênteses com o link de destino. Dentro dos parênteses contendo o link também é possível inserir um texto ao sobrepor o mouse. 

[Meu site](www.riss.com.br "Home de meu site")

Caso a necessidade de um link ou contato seja mais simples, apenas com o link de destino, o conteúdo pode ser inserido entre '<''>'

<https://www.riss.com.br>

--------------------------

## Citações ##

=> Citações podem ser destacadas ao inserir '>' no início das linhas da citação. 

> Este é um exemplo de citação.

--------------------------

## Listas ##

=> Listas não ordenadas podem ser criadas ao inserir '*' no inicio da linha e para subitens utilizando tabulação. 

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

=> Para listas ordenadas ao invés de utilizar o símbolo '*' devem sur utilizados os números.

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
   
=> Para listas ordenadas automaticamente é necessário apenas inserir '1.' em cada nova linha, ao renderizar o arquivo já ocorre a atualização dos números. 

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

=> Imagens presentes no diretório podem ser inseridas. É feito de forma semelhante à inserção de links, com necessidade de inserir o símbolo ! antes do primeiro colchete.

![et](media/et.png "et")

=> Imagens da web também podem ser inseridas da mesma forma.

![gif dev](https://riss.com.br/media/dev.gif "gif dev")

--------------------------

## Tabelas ##

=> Tabelas também podem ser inseridas, utilizando '|' para delimitar colunas e '-' para dividir cabeçalhos.

Potência | Valor 
---------|-------
10<sup>1</sup>|10
10<sup>2</sup>|100
10<sup>3</sup>|1000
10<sup>4</sup>|10000

Além do alinhamento padrão à esquerda, também pode ser definido como centralizado, inserindo ':' no inicio e no final da linha que indica a coluna desejada, ou à esquerda, inserindo ':' no final da linha que indica a coluna desejada.

Potência | Valor 
:-------:|-------:
10<sup>1</sup>|10
10<sup>2</sup>|100
10<sup>3</sup>|1000
10<sup>4</sup>|10000



Potência | Valor 
:-------:|-------:
10<sup>1</sup>|10
10<sup>2</sup>|100
10<sup>3</sup>|1000
10<sup>4</sup>|10000

--------------------------

## Texto de código ##

=> É possível inserir texto de código, que será renderizado em um bloco com destaque. Os hyperlinks ou recursos que seriam utilizados para renderização do markdown também são ignorados. Pode ser feito inserindo o código entre '``'.

`## Este é um exemplo de texto de código.## Recursos do markdown podem ser digitados aqui porém sem sua renderização, como em **negrito** ou _itálico_.`

Para blocos em várias linhas/parágrafos, o código deve ser inserido entre duas linhas contendo '```'.

```
#include <stdio.h>
#include <stdlib.h>

void main() {
    printf("Olá mundo!");
}
```

=> Ao inserir a linguagem ao lado dos sinais '```' presentes na primeira linha, o texto aparece em cores, respeitando as estruturas da linguagem 

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
