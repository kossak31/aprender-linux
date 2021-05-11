# aprender-linux
comandos básicos de linux

## prompt
a prompt é divida em 3 partes
PROMPT  = username
      	@ hostname
	      : current dir

exemplo final de uma prompt:
username@localhost:/directorio

para definir o tipo de username na prompt existe $ para utilizador e # para root

## pwd
como saber em que directorio estou ?
```
pwd - print working directory
```

## home
pasta com ficheiros do utilizador
```
~ atalho para home
cd ~ ou cd
```

## cd
mudar de directorio
```
cd - change directory

cd .. subir de directorio
cd ~ ou cd voltar ao home de utilizador
cd - voltar ao ultimo directorio visitado
```

## echo
```
echo -n sem quebra de linha
```

## caminhos relativos e absolutos
exemplo de um caminho absoluto: /home/jfc

exemplo de um caminho relativo: ../../jfc

## clear
limpar tela do terminal
```
clear
```
ou
<kbd>ctrl</kbd>+<kbd>l</kbd>

## history
ver comandos inseridos no terminal
```
history
```

## mkdir
criar directorio
```
mkdir - make directory
```
criar varios directorios mas parentes
```
mkdir -p directorio1/directorio2/directorio3
```

## rmdir e rm
### apagar directorio
```
rmdir - remove directory
```

### apagar ficheiro
```
rm - remove
```
```
-r recursiva com pasta cheia
-f force sem perguntas
```

## cat
ver ficheiro de texto
```
cat - concatenate
cat ficheiro.txt
```
ver ficheiro de texto a começar no fim
```
tac ficheiro.txt
```

## ls
listar ficheiros e directorios
```
ls - list

ls -l = long list
ls -la = ficheiros ocultos
ls -R = listar recursivamente
```

## regular expression
```
* = todos os caracteres
? = um caracter
```


## cp
copiar directorios e ficheiros
```
cp - copy
```
regras a saber sobre o copy:
um ficheiro não pode ter o mesmo nome que um directorio
```
cp <copia-origem> <copia-destino>
-r recursivamente
```

## head e tail

### head
```
head - mostra 10 primeiras linhas
head -n 4 - mostra as 4 primeiras linhas
```

### tail
```
tail - mostra 10 ultimas linhas
tail -n 4 - mostra as 4 ultimas linhas
```

## mv
mover ou renomear
```
mv - move
mv <origem> <destino>
mv <nome> <novo-nome>
```

## canais de comunicação
1. standart input
2. standart output
3. standart error


| stdin 1 teclado | programa |                   |
| ------------- |:-------------:| -----:|
|				          |          | stout 2 terminal  |
|				          |          | sterr 3 terminal  |




### redericionamento de output		
output de um comando ls para um ficheiro chamado a
```
ls > a
```

### append >>
append, nao estraga ou esmaga o ficheiro, adiciona ao final
```
cat a.txt >> b.txt
```

### redericionamento de input <
fazer copia sem o comando cp
```
cat < a > b
```

### ver erros num script
```
prog 2> erros.log
```

## wc
contar linhas, caracteres e palavras
```
wc - word count
-l linhas
-m caracteres
```

## pipe |
teclado/input ou prog | prog -> terminal

cmd | cmd

out -> input
```
echo y | cmd
ls | more
```

## diff
comparar ficheiros
```
diff ficheiro1.txt ficheiro2.txt
8d7 oitava linha
< PALAVRA no ficheiro esquerdo
```

## sudo
```
sudo - super user do
sudo cmd
```

alterar para root
```
sudo -i

sudo reboot
sudo shutdown -h 23:35
```

## more e less

### more
more só anda para a frente
```
more
```

### less
less permite andar para frente e para tras na tela
```
less

procurar no less - /
proxima referencia - m
```

## grep
procura e mostra referencia
```
cat a | grep asd
cat a | grep asd | wc -l
```

## vi
i insert
ESC
:q
sair sem gravar :q!
escrever ficheiro write :w
escrever e sair :wq
delete x
replace r
apagar linha dd
apagar 3 linhas 3dd
abre uma nova linha e abre edicao o
abre uma nova linha antes O



## tar
cria copia em tar da home
```
tar -cfv backup.tar /home/pbf
```

crie pasta teste e extrair para pasta teste
```
mkdir teste
tar xfv backup.tar -C /home/pbf/teste
```

visualizar lista de ficheiros
```
tar -tvf backup.tar
OU
tar --list --verbose --file=backup.tar 
```

### comprimir com gzip tar.gz
```
-czvf
```

### comprimir com bzip2 tar.bz2
```
-cjvf
```
