# Fluxo de Trabalho :information_source: #

Este arquivo procura mostrar algumas situações cotidianas onde o git pode ser usado e como agir, além de alguns modelos.

---

## Branch de homologação e de desenvolvimento ##

&xrArr; Em um fluxo de trabalho de desenvolvimento, é comum ter múltiplas branches. Por exemplo:

* Branch principal (main/master)
* Branch de homologação ou staging
* Branches de desenvolvimento: feat/tarefa-1; feat/tarefa-2; feat/tarefa-3...

---

### Branches de Desenvolvimento ###

&xrArr; Em um fluxo de trabalho ideal para o Git Flow simplificado, cada funcionalidade nova é uma nova branch criada com base na principal.

&xrArr; O código deve ser desenvolvido aqui.

&xrArr; É comum o uso do seguinte padrão para nomeação de branch:

* feat/tarefa-ou-funcionalidade &rarr; Novas funcionalidades ou melhorias
* fix/bug &rarr; Para correções de erros/comportamentos inesperados não críticos
* hotfix/correcao-urgente &rarr; Para erros críticos/que demandam solução imediata

&xrArr; Então ao começar uma nova tarefa por exemplo, o seguinte comando deve ser executado:

``` shell
git checkout -b feat/tarefa
```

&xrArr; Desta forma, a branch é criada e acessada.

&xrArr; Aqui o desenvolvimento e os testes iniciais em ambiente local são realizados.

---

### Branch de Homologação ###

&xrArr; Na branch de homologação ou staging, os testes e validações finais são realizados. Essa branch deve estar associada ao ambiente de homologação do sistema.

&xrArr; Após os testes locais, deve ser feito um merge da brach de desenvolvimento com a branch local.

``` shell
# Enviar a feat para o GitHub
git push origin feat/historico-sessoes

# Acessar branch de homolog e puxar ela para a máquina
git checkout homolog
git pull

# Trazer as novidades da feat para dentro da homolog
git merge feat/historico-sessoes
git push origin homolog
```

---

### Branch Principal ###

&xrArr; Uma vez homologado, o código pode ser adicionado a branch principal.

&xrArr; O processo pode ser realizado de forma similar à adição de código à branch de homologação. O conteúdo é puxado diretamente da branch de desenvolvimento.

``` shell
# Ir para a branch principal e puxar ela para a máquina
git checkout master
git pull

# Traz as novidades da feat para dentro da branch principal
git merge feat/historico-sessoes
git push origin master
```

---

#### Atualizando os ambientes de desenvolvimento e homologação ####

&xrArr; Pode ocorrer de durante o processo de desenvolvimento, a branch de homologação ou desenvolvimento precisar ser atualizada por interações de outras branches na branch principal.

&xrArr; Para esses casos são adotadas duas estratégias.

  1. git merge master &rarr; branch homologação
  2. git rebase master &rarr; branch desenvolvimento

---

##### Com a branch de homologação: Caso 1 #####

``` shell
# 1. Buscar na branch principal o código mais recente do servidor
git checkout master
git pull

# 2. Acessar e atualizar a branch de homologação
git checkout homolog
git pull 

# 3. Trazer as alterações da branch principal para dentro da homolog
git merge master

# 4. Enviar as atualizações de volta para o GitHub para atualizar o servidor da Vercel/Fly
git push origin homolog
```

&xrArr; Caso ocorra algum conflito, o git informará e será necessário resolver, definindo o que deve ser mantido.

&xrArr; Essa estratégia mantém o histórico de commits completo, importante para ambientes compartilhados.

---

##### Com a branch de desenvolvimento: Caso 2 #####

``` shell
# 1. Acessar a branch principal e atualizar o local
git checkout master
git pull

# 2. Acessar a branch de tarefa
git checkout feat/tela-professores

# 3. Aplicar o rebase com a branch principal
git rebase master
```

&xrArr; Caso ocorra algum conflito, o git informará e será necessário resolver, definindo o que deve ser mantido.

&xrArr; Após resolver um conflito, deve-se rodar:

`git rebase --continue`

&xrArr; O processo de resolução ocorre commit após commit até que todos os commits intermediários tenham sido preenchidos.

&xrArr; Essa estratégia atualiza o repositório criando um novo commit, o que gera um ambiente mais limpo.

&xrArr; __Push Forçado__: Caso já exista um push dessa feature para o GitHub antes do rebase, o Git vai recusar o push simples. Você precisará forçar o envio de forma segura usando:

`git push origin feat/nome-da-tarefa --force-with-lease`
> --force-with--lease realiza uma verificação do estado atual do repositório remoto e local. Caso sejam o mesmo, o commit é realizado, caso sejam divergentes, é mostrado erro.

## Vinculando e usando Issues ##

&xrArr; Para usar issues no fluxo de trabalho do git com github, é possível associar branches a issues. O processo pode ser feito via navegador ou colocando o nome da issue na branch relacionada.

`git checkout -b feat/1-ajuste-visual`

&xrArr; Ao enviar o commit de conclusão da tarefa, usar `closes #n` indica à plataforma que a issue deve ser fechada.

`git commit -m "feat: ajuste visual. Closes #1"`

## Finalizando tarefas ##

&xrArr; Ao concluir tarefas, após encerrar a atividade e finalizar issues vinculadas, a branch de trabalho pode ser deletada.

``` shell
# 1. Acessar a branch principal 
git checkout master

# 2. Deletar a branch localmente
git branch -d feat/1-tarefa

# 3. Deletar a branch no servidor remoto
git push origin --delete feat/1-tarefa
```
