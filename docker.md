# Comandos de terminal Docker

_Os comandos são uma parte da utilização da tecnologia, é preciso estudar também os arquivos, etc._

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

## `docker stop`
pára containers em execução

### `docker stop -t`
"time"  
define quantos segundos esperar, antes de forçar o encerramento (o padrão é 10)