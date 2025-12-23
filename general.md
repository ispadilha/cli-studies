# Comandos de terminal em geral

_Estes comandos estão disponíveis em diversos Sistemas Operacionais, de forma geral, embora não sejam nativos de todos eles._

---

## `mysql`
acessa o cliente de linha de comando do servidor MySQL

### `-h`
especifica o host do servidor MySQL  
se omitido, assume localhost

### `-u`
especifica usuário

### `-p`
especifica senha  
não se recomenda passar senhas diretamente em linha de comando, pois podem ficar visíveis no histórico ou em processos do sistema  
sendo omitida (conforme recomendação), será solicitada interativamente no terminal

```mysql -h <host> -u <user> -p```

---

## `ping`
testa se um host está acessível na rede e mede o tempo de resposta  
usa-se o comando seguido de um endereço a ser testado

---

## `traceroute`
mostra os saltos (hops) da rota percorrida pelos pacotes até o destino  
usa-se o comando seguido de um endereço a ser testado  
no Windows, usa-se `tracert`