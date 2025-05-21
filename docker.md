# Comandos de terminal Docker

_Os comandos são uma parte da utilização da tecnologia, é preciso estudar também os arquivos, etc._

---

## `docker exec`
"execute"    
executa comandos dentro de containers em execução

### `docker exec -it`
"interactive"   
abre um terminal interativo dentro do container

### `docker exec -d`
"detached"   
executa o comando em background

---

## `docker image`
gerencia imagens docker

### `docker image ls`
"list"  
lista as imagens disponíveis localmente

### `docker image rm`
"remove"  
remove uma imagem docker

### `docker image pull`
faz download de uma imagem docker do docker hub, ou outro registry configurado

---

## `docker ps`
"process status"    
inspirado no comando `ps` em linux/unix     
exibe os containers ativos

### `docker ps -a`
"all"   
exibe todos os containers, inclusive os que estiverem parados

### `docker ps -q`
"quiet"     
exibe "silenciosamente" apenas os IDs dos containers ativos, sem uma tabela com outros dados   
sendo assim, é útil em scripts ou comandos encadeados

---

## `docker run`
cria e inicia um novo container a partir de uma imagem  
é capaz de, inclusive, baixar a imagem se ainda não estiver presente    
pode ser seguido de opção, imagem e comando     

### `docker run -d`
"detached"  
roda em background

### `docker run --env`
"environment"   
define variáveis de ambiente

### `docker run -it`
"interactive"   
abre um terminal interativo

### `docker run --name`
dá um nome personalizado ao container

### `docker run -p`
"ports"     
faz mapeamento de portas entre o host e o container

### `docker run --rm`
"remove"    
remove o container automaticamente, após ele parar

### `docker run -v`
"volumes"   
faz mapeamento de volumes no container

---

## `docker start`
inicia um container que esteja parado

### `docker start -a`
"attach"    
anexa o terminal do container ao atual, mostrando sua saída padrão  
caso seja usado sozinho, não aceita entrada, por isso é comumente usado junto com `docker start -i`

### `docker start -i`
"interactive"   
direciona a entrada padrão ao terminal do container     
caso seja usado sozinho, não exibirá saída, por isso é comumente usado junto com `docker start -a`

---

## `docker stop`
pára containers em execução

### `docker stop -t`
"time"  
define quantos segundos esperar, antes de forçar o encerramento (o padrão é 10)