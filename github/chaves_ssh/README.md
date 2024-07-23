## Introdução :information_source: ##

&xrArr; O GitHub solicita autenticação com chaves SSH para acesso e operação em repositórios. Chaves SSH são criadas e devem ser adicionadas ao agente SSH para que o GitHub aceite a autenticação. Também devem ser vinculadas em uma conta de usuário do GitHub.

&xrArr; https://docs.github.com/en/authentication/connecting-to-github-with-ssh

---

## Gerando a chave SSH (processo em comum nas plataformas) :old_key: ##
 
&xrArr; O comando abaixo permite a criação de uma chave SSH: 

`$ ssh-keygen -t ed25519 -C "<email>"`

A inclusão da chave ocorrerá, por padrão, no arquivo id_ed25519, na pasta .ssh que é criada na pasta do atual usuário. 

Para alterar o diretório é possível utilizar o comando acima com o comando -f juntamente do caminho desejado:

`$ ssh-keygen -t ed25519 -C "<email>" -f <caminho_do_diretorio>/.ssh/id_ed25519`

O email inserido pode ser o email de cadastro no GitHub. Durante a criação também será solicitada criação de uma senha.

---

## Adicionando a chave SSH ao agente :shipit: ##

&xrArr; Uma vez adicionada é necessário adicionar a chave ao agente:

`$ ssh-add <caminho_do_arquivo_criado_acima>`

É possível listar as chaves adicionadas ao agente através do comando:

`ssh-add -l`

Para remover todas chaves do agente é possível através do comando:

`ssh-add -D`

Este comando apenas remove as chaves do agente, não apaga os arquivos.

---

## Para iniciar automaticamente as chaves SSH ao agente no início de uma sessão do terminal :arrow_forward::shipit: ## 

&xrArr; Por padrão o agente SSH não armazena as chaves SSH adicionadas. Portanto em novos inícios de sessão, é necessário fazer o cadastro das chaves ao agente. Para fazer esse processo de início automático um script deve ser adicionado aos arquivos de inicialização do terminal. 

&xrArr; Em ambos scripts é necessário alterar `<caminho_do_arquivo_com_chave_ssh>` para o caminho da chave SSH criada. 

### No Windows :key::window: ###

&xrArr; No final do arquivo .profile ou no arquivo .bashrc, ambos presentes na pasta do usuário:

`~/.profile`

`~/.bashrc`

O código abaixo deve ser adicionado:

``` shell
env=~/.ssh/agent.env

agent_load_env () { test -f "$env" && . "$env" >| /dev/null ; }

agent_start () {
    (umask 077; ssh-agent >| "$env")
    . "$env" >| /dev/null ; }

agent_load_env

# agent_run_state: 0=agent running w/ key; 1=agent w/o key; 2=agent not running
agent_run_state=$(ssh-add -l >| /dev/null 2>&1; echo $?)

if [ ! "$SSH_AUTH_SOCK" ] || [ $agent_run_state = 2 ]; then
    agent_start
    ssh-add <caminho_do_arquivo_com_chave_ssh>
elif [ "$SSH_AUTH_SOCK" ] && [ $agent_run_state = 1 ]; then
    ssh-add <caminho_do_arquivo_com_chave_ssh>
fi

unset env
```

### No Linux :key::penguin: ###

&xrArr; No final do arquivo bash.bashrc presente em /etc:

`/etc/bash.bashrc`

Pode ser adicionado o seguinte comando: 

```
ssh-add <caminho_do_arquivo_com_chave_ssh>
```

---

## Adicionando a chave no GitHub :key::octocat: ##

&xrArr; Com a chave adicionada ao agente SSH, é necessário adicioná-la no GitHub:

`perfil > settings > SSH and GPG keys > new SSH key.`

Deve ser inserido o conteúdo do arquivo id_ed25519.pub, este arquivo é criado juntamente do arquivo que contém a chave SSH (id_ed25519), porém este possui os valores públicos para a chave SSH. O arquivo está no mesmo diretório que foi criada a chave SSH.
