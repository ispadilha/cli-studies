# Comandos de terminal Linux

Este não é um material qualquer, copiado e colado de algum lugar. Trata-se de um compilado de comandos já usados e estudados por mim, e existe para fixação do aprendizado e possibilidade de consulta.

_Esta lista é um trabalho em eterno progresso..._

---

### `--help`  
opção que funciona com mais de um comando, exibe informações para ajuda no uso do mesmo

---

## `cat`  
“concatenate”  
além de concatenações, pode ser usado para mostrar conteúdo de um arquivo no terminal   
neste último caso de uso, é melhor para arquivos curtos, pois exibe todo o conteúdo do arquivo de uma vez, e não permite rolagem ou navegação    
para arquivos longos e quando se deseja estas funcionalidades, é melhor usar `more` ou `less`

---

## `cd`  
“change directory”  
muda de diretório (“navega”) para o diretório especificado  
quando usado sem especificar nenhum, volta para a home do usuário atual

---

## `clear`  
limpa o terminal

---

## `cp`  
“copy”  
copia arquivos e diretórios

---

## `echo`  
imprime o texto após o comando, útil para tornar scripts informativos

---

## `exit`  
sai do modo super usuário e de algumas outras aplicações

---

## `help`  
exibe lista de comandos e ferramentas do shell  
interessante notar que são estes comandos que não funcionam acompanhados do `sudo`, porque alteram o estado do shell    
portanto, para serem executados por super usuário, é necessário elevar todo o shell primeiro

---

## `less`
"less is more"  
nomeado a partir deste trocadilho, o comando é semelhante ao `cat`, pois exibe o conteúdo de um arquivo no terminal     
é melhor para arquivos grandes, pois permite visualização interativa    
é semelhante também ao `more`, sendo algo como uma versão modernizada do mesmo, pois permite voltar e avançar no texto, tem busca por regex, e aceita atalhos de navegação estilo vi

---

## `ls`  
“list”  
lista o conteúdo do diretório atual

### `ls -a`  
“list all”  
lista todos os arquivos e diretórios no diretório atual, inclusive ocultos

### `ls -l`  
“list long”  
lista arquivos e diretórios com detalhes, incluindo permissões e proprietários

---

## `man`  
“manual”  
é usado seguido de outro comando e exibe manual de uso do mesmo

---

## `mkdir`  
“make directory”  
cria um novo diretório com o nome especificado

---

## `more`
comando semelhante ao `cat` e ao `less`, para exibir conteúdo de um arquivo no terminal     
é um meio termo entre estes comandos acima, pois é melhor do que o `cat` para arquivos longos, porém é mais antigo e tem menos funcionalidades do que o `less`

---

## `mv`  
“move”  
move um arquivo ou diretório para outro diretório  
caso não seja especificado outro diretório, renomeia no diretório atual

---

## `pwd`  
“print working directory”  
imprime o caminho do diretório atual

---

## `rm`  
“remove”  
remove arquivos ou diretórios com arquivos, sendo que para este último caso é necessário usar certos atributos

### `rm -f`  
“remoção forçada”

### `rm -i`  
“remoção interativa”  
solicita confirmação antes de efetivamente remover um arquivo ou diretório

### `rm -r`  
“remover recursivamente”  
usado para remover diretórios com arquivos

---

## `rmdir`  
“remove directory”  
remove diretório vazio

---

## `sudo`  
“super user do”  
executa comando seguinte como super usuário (com permissão/”privilégios”)

### `sudo -i` ou `sudo su`  
inicia sessão como root (super usuário) no terminal  
(para comandos que alteram o estado do terminal e não funcionam com sudo)

---

## `touch`  
cria um novo arquivo com o nome especificado
