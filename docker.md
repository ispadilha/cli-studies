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

### `docker build --no-cache`
"sem cache"   
desativa o uso de cache durante o build da imagem   
normalmente, para cada instrução no Dockerfile, o docker tenta reutilizar camadas já construídas, neste caso isso é desativado   
isso deixa o processo mais lento, mas é útil ao depurar problemas

> docker build -t \<container> . --no-cache

---

## `docker compose`
gerencia aplicações multi-container definidas em um arquivo docker-compose.yml

### `docker compose up`
inicia os serviços definidos no arquivo docker-compose.yml

### `docker compose up -d`
"detached"  
inicia os serviços em background

### `docker compose down`
pára e remove os containers, redes e volumes criados pelo compose

### `docker compose build`
constrói ou reconstrói as imagens dos serviços

### `docker compose logs`
mostra os logs dos serviços

### `docker compose ps`
lista os containers dos serviços em execução

### `docker compose -f`
"file"  
especifica um arquivo compose diferente do padrão (docker-compose.yml)

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

## `docker cp`
copia arquivos entre o host e o container

> docker cp \<container>:/caminho/no/container /caminho/no/host
>
> docker cp /caminho/no/host \<container>:/caminho/no/container

---

## `docker exec`
"execute"    
executa comandos dentro de containers em execução

### `docker exec -it`
"interactive"   
mantém a entrada padrão (STDIN) aberta   
"tty"   
cria um terminal virtual   
estas duas flags são quase sempre usadas juntas, e ao final do comando especifica-se um terminal (por exemplo, bash)   
na prática, o comando "faz o terminal entrar no container"

> docker exec -it \<container> /bin/bash

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

## `docker push`
"empurra" uma imagem local para o docker hub ou outro registry remoto configurado   
requer que a imagem esteja corretamente etiquetada ("tagueada") e que o usuário esteja autenticado no registry

> docker push \<container>

---

## `docker restart`
reinicia um container

> docker restart \<container>

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
