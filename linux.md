# Comandos de terminal Linux

_Lista feita e estudada em Ubuntu. Talvez eu separe em novas listas por distros, futuramente._

---

### `--help`  
opção que funciona com mais de um comando, exibe informações para ajuda no uso do mesmo

---

## `cat`  
"concatenate"  
além de concatenações, pode ser usado para mostrar conteúdo de um arquivo no terminal   
neste último caso de uso, é melhor para arquivos curtos, pois exibe todo o conteúdo do arquivo de uma vez, e não permite rolagem ou navegação    
para arquivos longos e quando se deseja estas funcionalidades, é melhor usar `more` ou `less`

---

## `cd`  
"change directory"  
muda de diretório ("navega") para o diretório especificado  
quando usado sem especificar nenhum, volta para a home do usuário atual

---

## `chmod`
"change mode"   
altera modos de permissões de arquivos  
é seguido do novo modo de permissões, e depois do caminho do arquivo

---

## `clear`  
limpa o terminal

---

## `cp`  
"copy"  
copia arquivos e diretórios

---

## `echo`  
imprime o texto após o comando, útil para tornar scripts informativos

---

## `exit`  
sai do modo super usuário e de algumas outras aplicações

---

## `head`
exibe as primeiras linhas de um arquivo, sendo que por padrão exibe 10

### `head -n`
exibe as "n" primeiras linhas de um arquivo, em número especificado

---

## `help`  
exibe lista de comandos e ferramentas do shell  
interessante notar que são estes comandos que não funcionam acompanhados do `sudo`, porque alteram o estado do shell    
portanto, para serem executados por super usuário, é necessário elevar todo o shell primeiro

---

## `history`
exibe o histórico de comandos executados no terminal

---

## `htop`
"human-friendly top processes"    
semelhante ao comando `top`, lista os processos no "topo" de uso dos recursos do sistema   
é uma versão "modernizada" ou mais "amigável" quanto a sua interface gráfica    
ao contrário do `top`, no entanto, nem sempre vem instalado com a distro, mas sua instalação é fácil e geralmente está nos repositórios oficiais 

---

## `kill`
como o nome sugere, "mata" (encerra imediatamente) um processo  
usa-se seguido do devido PID (process ID), que pode ser consultado com o comando `ps aux` por exemplo

### `kill -STOP`
faz um determinado processo parar   
é possível retomar a execução depois, dependendo do processo

### `kill -CONT`
"continue"  
retoma a execução de um processo que foi parado com `kill -STOP`, se possível

### `kill -9`
mata um processo de forma abrupta   
com isso, o processo não tem tempo de salvar informações, liberar memória, etc      
isso é indesejado, portanto usar apenas se necessário

---

## `less`
"less is more"  
nomeado a partir deste trocadilho, o comando é semelhante ao `cat`, pois exibe o conteúdo de um arquivo no terminal     
é melhor para arquivos grandes, pois permite visualização interativa    
é semelhante também ao `more`, sendo algo como uma versão modernizada do mesmo, pois permite voltar e avançar no texto, tem busca por regex, e aceita atalhos de navegação estilo vi

---

## `ls`  
"list"  
lista o conteúdo do diretório atual

### `ls -a`  
"list all"  
lista todos os arquivos e diretórios no diretório atual, inclusive ocultos

### `ls -l`  
"list long"  
lista arquivos e diretórios com detalhes, incluindo permissões e proprietários

---

## `man`  
"manual"  
é usado seguido de outro comando e exibe manual de uso do mesmo

---

## `mkdir`  
"make directory"  
cria um novo diretório com o nome especificado

---

## `more`
comando semelhante ao `cat` e ao `less`, para exibir conteúdo de um arquivo no terminal     
é um meio termo entre estes comandos acima, pois é melhor do que o `cat` para arquivos longos, porém é mais antigo e tem menos funcionalidades do que o `less`

---

## `mv`  
"move"  
move um arquivo ou diretório para outro diretório  
caso não seja especificado outro diretório, renomeia no diretório atual

---

## `nslookup`
"name server lookup"    
usado para consultar DNS, ou seja, obter informações sobre nomes de domínio e endereços IP  
o comando pode ser seguido de um domínio ou um endereço IP: fornecendo um, retorna o outro  
é possível especificar um servidor DNS para uso, entre o comando e o domínio ou endereço    
ao ser usado puro, o comando inicia um modo interativo, que aceita inputs como os seguintes:     

### `set type=A`
registros de endereço IPv4

### `set type=AAAA`
registros de endereço IPv6

### `set type=MX`
servidores de e-mail

### `set type=NS`
servidores DNS autoritativos

### `set type=TXT`
registros de texto

---

## `pkill`
"process kill"  
semelhante ao `kill`, mas se especifica o nome do processo, ao invés de seu PID

---

## `ps`
"process status"    
exibe os processos em execução

### `ps aux`
"process status auxiliary"  
exibe processos em execução de forma mais ampla, abrangendo processos em mais estados no momento da execução do comando, e mais colunas de informações

### `ps aux --sort`
exibe os processos em execução, ordenados por um parâmetro especificado

### `ps -u`
"process status of user"    
exibe os processos em execução de um determinado usuário especificado

### `ps -C`
"process status of command"     
exibe informações referentes a um determinado processo em execução, especificado pelo nome de seu comando

---

## `pstree`
"process status tree"   
semelhante ao `ps`, também exibe processos em execução, mas de forma esquematizada em uma árvore

---

## `pwd`  
"print working directory"  
imprime o caminho do diretório atual

---

## `rm`  
"remove"  
remove arquivos ou diretórios com arquivos, sendo que para este último caso é necessário usar certos atributos

### `rm -f`  
"remoção forçada"

### `rm -i`  
"remoção interativa"  
solicita confirmação antes de efetivamente remover um arquivo ou diretório

### `rm -r`  
"remover recursivamente"  
usado para remover diretórios com arquivos

---

## `rmdir`  
"remove directory"  
remove diretório vazio

---

## `ssh`
"secure shell"  
permite conexão remota  
para funcionar, é necessário que chaves estejam configuradas    
ou seja, arquivos que contenham chaves criptográficas estejam nos locais (diretórios) corretos, ou corretamente referenciados, no servidor remoto (chave pública) e na máquina local (chave privada)   

### `ssh -i`
"secure shell identify"     
precede as identificações necessárias para fazer a conexão remota   
na máquina local, é o caminho para o arquivo com a chave privada    
no servidor remoto, é usuário@endereço

### `ssh-keygen`
gera chaves, ou seja, cria arquivos que contém chaves criptográficas, para diferentes fins

---

## `sudo`  
"super user do"  
executa comando seguinte como super usuário (com permissão/"privilégios")

### `sudo -i` ou `sudo su`  
inicia sessão como root (super usuário) no terminal  
(para comandos que alteram o estado do terminal e não funcionam com sudo)

---

## `tail`
exibe as últimas linhas de um arquivo, sendo que por padrão exibe 10

### `tail -n`
exibe as "n" últimas linhas de um arquivo, em número especificado

---

## `top`
"top processes"     
lista os processos que mais consomem recursos no momento, como processamento e memória  
ou seja, ele mostra os processos que estão no topo da atividade do sistema  
possui uma versão modernizada, o `htop`

---

## `touch`  
cria um novo arquivo com o nome especificado

---

## `xkill`
semelhante a `kill` e `pkill`, também se destina a matar processos, porém é usado em ambiente gráfico   
após se emitir o comando, deve-se clicar na janela do referido processo     
portanto, ela precisa estar vísivel