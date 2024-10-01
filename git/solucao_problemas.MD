# Arquivo de problemas e soluções no git0 #

## old mode new mode :older_adult: :baby: ##

&xrArr; Algumas vezes trabalhando com repositórios remotos pode ocorrer de aparecer em muitos arquivos do repositório modificações não identificadas pelo usuário, e ao rodar o comando `git diff` será retornado que os arquivos foram alterados em:

``` 
old mode 100644
new mode 100755
```

&xrArr; Este erro pode acontecer ao trabalhar com repositórios com fork e criar branchs por exemplo. Neste caso, a diferença indica, através dos metadados do arquivo, uma alteração de estado de não executável para executável. 

&xrArr; Para que as alterações desse tipo não sejam mapeadas pelo git como uma alteração de arquivo e gerar volumes desnecessários nos commits, o seguinte comando pode ser rodado: 

``` shell
$ git config core.filemode false
```

---
