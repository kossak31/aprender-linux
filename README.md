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

## gzip e bzip2
bzip2 mais lento mas mais compressao

### gzip
comprimir ficheiro e apagar original
```
gzip ficheiro.txt
```

nao apagar ficheiro original
```
gzip -k ficheiro.gz
```

listar detalhes
```
gzip -l ficheiro.gz
```

teste de integridade
```
gzip -tv ficheiro.gz
```

force
```
gzip -f ficheiro.gz
```

gzip recursisamente
```
gzip -r *
```


concatenar ficheiros.gz
```
gzip -c file1.txt > files.gz
gzip -c file2.txt >> files.gz
```




descomprimir ficheiro
```
gzip -d ficheiro.gz	
gunzip ficheiro.gz
gunzip -c file.gz > file.txt
```

### bzip2
```
bzip2 list.txt
bzip2 list.txt list1.txt list2.txt
```

descomprimir ficheiro bz2
```
bzip2 -d list.txt.bz2
bunzip2 list.txt.bz2
```

por padrao os ficheiros originais sao apagados -k para nao apagar
```
bzip2 -k ficheiro.bz2
```


## dd
/dev/null
/dev/zero escreve zero
/dev/random gerar numeros

```
dd if=/dev/zero of=abc bs=1M count=10
```

zerar primeiros 10 megas
```
dd if=/dev/zero of=/dev/sda bs=1M count=10
```

formatar sda primeiros 10 megas
```
dd if=/dev/random of=/dev/sda bs=1M count=10
```

bc
```
echo 4+4 | bc
```

calendario
```
cal
```

data
```
date
```


disk usage
```
du
```

desligar sistena
```
shutdown
```

reiniciar sistema
```
reboot
```

suspender programa por x tempo
```
sleep
```

descarrega ficheiros por http e ftp
```
wget
```

historico da linha de comandos
```
history
history -c
history -d <nº de linha>
```

tempo de actividade
```
uptime
```

## apt

| Command | Description |
| --- | --- |
| `update` | update dos ultimos pacotes |
| `upgrade` | upgrade de pacotes |
| `install` | instalar os pacotes |
| `remove` | remove apenas ficheiros binarios e deixa as configuracoes |
| `purge` | remove tudo relacionado com o pacote incluido os ficheiros de configuracao |
| `full-upgrade` novo `dist-upgrade` | actualiza a distribuição pela mais recente |
| `search` | procura pelo pacote |
| `show` | mostra info sobre o pacote |
| `autoremove` ou `auto-remove` | remove pacotes sem dependecias |
| `auto-clean` | remove pacotes em cache |
| `apt-key list` | lista as chaves dos repositorios |
| `apt-key del` | remove chaves dos repositorios |
| `apt-file` | para procurar ficheiros usados util para bibliotecas |



## gerir partições

permite listar todos os dispositivos orientados ao bloco
```
lsblk
```

permite manipular partições e podemos utilizá-lo para verificar que partições existem e se são MBR ou GPT
```
parted
```



permitem gerir as partições em MBR e GPT
```
fdisk e gdisk
```

formatar partições utilizando o formato ext4
```
mkfs.ext4
```


permite montar uma partição numa determinada pasta do sistema operativo de forma manual
```
mount
```

verificar espaço disponivel
```
df
```

permite fazer unmount do sistema de ficheiros
```
umount
```




em vez de utilizamos /dev/sdb1 podemos utilizar "videos"
```
sudo tune2fs -L videos /dev/sdb1
```


verificar as várias informações de uma partição através da opção -l
```
sudo tune2fs -l /dev/sdb1
```

ponto de montagem
```
sudo mkdir /videos
```


criação dos ficheiros de cońfiguração do systemd

## criar ficheiro videos.mount
/etc/systemd/system/videos.mount

```
[Unit]
Description=Mount unit for videos
[Mount]
What=LABEL=videos
Where=/videos
Type=ext4
Options=defaults

[Install]
WantedBy=multi-user.target
```


videos.automount
```
[Automount]
Where=/videos

[Install]
WantedBy=multi-user.target
```

```
sudo systemctl daemon-reload
sudo systemctl enable --now videos.automount
```

verificar se foi correctamente montado, utilizando o comando mount



## Secure Shell
O Secure Shell é um protocolo de rede (cifrado) que permite o acesso remoto a máquinas de forma segura, num
paradigma de cliente-servidor. O serviço dá acesso a um terminal remoto para a
execução de comandos.

instalar serviço de ssh
```
sudo apt install openssh-server
```


O ficheiro de configuração sshd_config
```
/etc/ssh/sshd_config
```

opções para alterar
```
Port
ListenAddress
PermitRootLogin
PasswordAuthentication
UseDNS
```

iniciar o serviço
```
systemctl stop,start,status,restart
```

instalar cliente ssh
```
sudo apt install openssh-client
```

para estabelecer uma ligação na porta 22
```
ssh username@servername
```

