## Introdução ##

O GitHub é uma plataforma que pode servir como um hospedeiro para um repositório central do Git. É útil pois permite o uso em rede de um repositório Git, além de ser um útil portfolio para desenvolvimento. Através da sua página web é possível acessar repositórios e também editar.

---

## Início ##

&xrArr; Ao trabalhar com repositórios no github é necessário inicialmente criar o repositório na plataforma. Este repositório criado atua como um bare repository.

&xrArr; Uma vez criado, deve ser replicado em um diretório na máquina local 
    
`$ git init`

`$ git add README.md`

`$ git commit -m 'Primeiro commit'`

`$ git remote add origin <url do repositório do github>`

`$ git push -u origin master`

A opção -u em push permite indicar o ponto de referência para operações. No caso, estamos indicando a branch master em origin como branch de referência

&xrArr; O GitHub possui necessidade de configuração de chave SSH para realizar operações em seus repositórios. Como existe necessidade de atividades externas ao git e ao GitHub, [este repositório](chaves_ssh) possui instruções relativas a elas. 

Portanto, para realizar pushs e pulls para o repositório no GitHub é necessário configurar o agente SSH na máquina.

---

## Buscando um repositório no GitHub ##

&xrArr; Uma vez com uma conta autenticada é possível trabalhar com os repositórios do GitHub. Para trabalhar com um repositório disponível no GitHub:

`Acessar o repositório > Página inicial > Code`

Geralmente o link SSH é composto por: 

`git@github.com:<usuario dono do repositorio>/<nome do_repositorio>.git. `

Através do link do repositório é possível realizar um clone do mesmo em diretório em uma máquina local, assim permitindo pushs e pulls no repositório. 

---

## Visibilidade e acesso ##

&xrArr; Para repositórios privados, apenas os usuários do Git com uma conta vinculada ao projeto ou usuários com a chave SSH cadastrada em uma conta vinculada ao projeto podem ver e realizar alterações. 
    
&xrArr; Já repositórios públicos podem ser vistos por todos e podem ser ser realizados clones e pulls por todos usuários. 

Uma vez clonado para um repositório na máquina local do usuário, o mesmo pode trabalhar localmente com ele. Porém apenas usuários autorizados podem realizar push

&xrArr; Para alterar a visibilidade de um repositório
    Acessar o repositório > Settings > Danger Zone > Change repository visibility

&xrArr; Para alterar os usuários com permissão de acesso ao projeto
    Acessar o repositório > Settings > Collaborators

---

## Visualização na tela inicial ##

&xrArr; Na página inicial do projeto é possível visualizar itens relativos a informações como commits, tags e branchs. Estas opções permitem navegar no projeto de forma visual similar ao uso de checkout no terminal.

---

## Issues ##

&xrArr; Issues permitem inserir apontamentos de erros no projeto. Dentro da página inicial do projeto é possível ver a aba 'Issues', onde é possível visualizar as issues relacionadas ao projeto.

Também é possível incluir novas (com descrição, atribuição de responsável, categoria, etc). Usuários externos ao projeto podem apenas criar novas issues para projetos abertos.

Portanto, cabe aos responsáveis pelo projeto atribuir o responsável pela correção, classificação, encerrar uma issue e outras ações. Dentro desse processo, pode ser avaliado se a issue realmente deveria ser aberta.

Ao realizar a correção de uma issue, é possível indicar na mensagem do commit com a correção que a issue deve ser encerrada, assim ao realizar o push a issue é encerrada automaticamente. A referência utilizada é o número da issue: 
        
`$ git commit -m '... Closes #<numero_issue>'`

---

## Fork ##

&xrArr; Em projetos de código aberto de outros usuários é possível realizar um fork através da tela inicial do repositório. Isso cria uma cópia independente do repositório na conta que realizou o fork, permitindo que sejam realizadas alterações e teste de forma autônoma. As operações futuras em ambos repositórios não ocasionarão em interferências entre si.     

---

## Pull request ##

&xrArr; Caso as alterações feitas em um repositório que foi feito fork sejam satisfatórias e o realizador possua interesse em submeter o código ao projeto principal, é possível realizar um pull request. Assim é criada uma solicitação para o responsável pelo projeto para analisar e aceitar ou não a alteração.

&xrArr; Uma estratégia para auxiliar na análise do conteúdo recebido com a solicitação é realizar a criação de uma nova branch do projeto alterado. Caso as alterações sejam válidas, é possível realizar um merge na main do projeto principal. 

O comando abaixo permite criar uma nova branch e realizar o fetch:

`$ git fetch origin pull/<numero_request>/head:<nome_nova_branch>`

&xrArr; Após analisar o pull request e tomar as devidas ações, é possível encerrar a solicitação no commit informando o seu número, da mesma forma que uma issue.

`$ git commit -m '... Closes #<numero_pull_request>'`

---

## Gists ##

&xrArr; Gists fornecem uma forma simples de compartilhar snippets de código. Desta forma, trechos de código curtos para auxílio ou armazenamento podem ser salvos no GitHub.

&xrArr; Gists são repositórios do Git, portanto é possível realizar fork, clone e acompanhar seu histórico de commit. 

&xrArr; Também, assim como repositórios, podem ser criados como públicos ou privados. Porém um git criado como público não pode ser convertido para um gist secreto. 

https://docs.github.com/en/get-started/writing-on-github/editing-and-sharing-content-with-gists/creating-gists
    
