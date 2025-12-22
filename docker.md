# Comandos de terminal Docker

_Os comandos são uma parte da utilização da tecnologia, é preciso estudar também os arquivos, etc._

---

## `docker build`
cria uma nova imagem docker a partir de um Dockerfile presente no diretório atual

### `docker build -f`
"file"  
cria uma nova imagem docker a partir de um Dockerfile presente no caminho especificado após a opção

### `docker build -t`
"tag"    
define uma tag para a imagem docker que será criada

---

## `docker container`
gerencia containers já existentes   
a maioria dos comandos tem efeitos iguais a outros comandos mais curtos

### `docker container inspect`
mostra detalhes do container

### `docker container logs`
mostra logs do container

### `docker container ls`
"list"  
lista os containers ativos

### `docker container ls -a`
"list all"  
lista todos os containers, inclusive os que estiverem parados

### `docker container prune`
"poda"    
remove todos os containers parados, após uma pergunta de confirmação

### `docker container prune -f`
"poda forçada"  
remove todos os containers parados sem perguntar por confirmação

### `docker container rm`
"remove"  
remove um container

### `docker container start`
inicia um container parado

### `docker container stop`
pára um container em execução

---

## `docker exec`
"execute"    
executa comandos dentro de containers em execução

### `docker exec -it`
"interactive"   
mantém a entrada padrão (STDIN) aberta   
"tty"   
cria um terminal virtual   
estas duas flags são quase sempre usadas juntas   
na prática, o comando faz o terminal "entrar" no container

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

## `docker restart`
reinicia um container, cujo nome é especificado após o comando

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

---

## `docker system`
gerencia o estado geral do docker no sistema

### `docker system df`
"disk free"     
mostra o uso de disco por imagens, containers, volumes e caches

### `docker system events`
exibe eventos do Docker em tempo real (logs do daemon)

### `docker system info`
mostra informações gerais do sistema Docker (versão, número de containers, drivers, etc.)

### `docker system prune`
"poda" tudo que não está sendo usado (containers, imagens, redes, volumes)