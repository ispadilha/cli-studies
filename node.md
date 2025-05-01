# Comandos de terminal Node

_Node é um ambiente de execução de JavaScript. Anteriormente, esta linguagem se resumia a páginas na Internet e navegadores. Com o Node, pode agora ser usada em servidores, APIs, scripts, terminal em geral._

---

## `node`
inicia o REPL do node   
"read / evaluate / print / loop"    
o REPL é um ambiente interativo onde se pode executar comandos diretamente, e ver os resultados imediatamente   
quando usado seguido de um arquivo de script, irá executar o conteúdo do mesmo
 
### `node -v`
"version"   
mostra a versão instalada

---

## `npm`
"node package manager"  
ferramenta de gerenciamento de pacotes do Node.js   
estes "pacotes" são bibliotecas ou módulos reutilizáveis de código, produzidos por outras pessoas e publicados no registro do npm   
podem ser instalados com o comando `npm install`   
eles são armazenados na pasta node_modules/ e listados no arquivo package.json

---

## `npm init`
inicializa um projeto Node.js no diretório atual, criando o arquivo package.json    
a inicialização do projeto é interativa, com perguntas sobre versão, autor, licença, etc
 
### `npm init -y`
inicializa um projeto Node.js no diretório atual, criando o arquivo package.json com as opções padrão   
ou seja, "pula" a etapa de perguntas

---

## `npm install`
instala pacotes do Node.js, especificados após o comando    
quando usado puro, o comando lê os pacotes no arquivo package.json e as versões de cada pacote no arquivo package-lock.json, e reconstrói o diretório node_modules/

### `npm install -g`
instala pacotes de forma global, ou seja, poderão ser usados em qualquer lugar do sistema, não apenas dentro de um projeto específico

---

## `npm run`
é usado para executar qualquer script definido na seção "scripts" do arquivo package.json   
quando executado puro, exibe os scripts disponíveis

---

## `npm start`
é um atalho para o script "start", comumente presente no arquivo package.json   
é a mesma coisa que `npm run start`     
caso não haja um script "start", este comando tentará rodar `node server.js` (comportamento legado)