# Comandos de terminal Git

Compilado de comandos já usados e estudados por mim, para fixação do aprendizado e possibilidade de consulta.

---

## `git add`
adiciona arquivos ao "stage", para serem submetidos a um commit

---

## `git branch`
administra "branches" em um repositório git

### `git branch -d`
deleta uma determinada branch do repositório local  
útil para manter o repositório "enxuto" após a referida branch ter sido mesclada à main, por exemplo    
é importante notar que isso não deleta a referida branch no repositório remoto, para isso é necessário usar `git push origin :`

### `git branch -M`
"move" (renomeia) o nome da branch atual para um novo nome especificado     
historicamente, a branch padrão criada juntamente com o repositório era chamada "master"    
atualmente, é uma boa prática renomear para "main"

---

## `git checkout`
muda para uma branch especificada, ou restaura arquivos     
pelo fato de poder mudar o estado do repositório, é um comando versátil que possui diferentes funcionalidades   
no entanto, por isso mesmo acabou se mostrando confuso, e em seu lugar foram criados novos comandos

### `git checkout HEAD --`
restaura um arquivo especificado para seu estado no último commit (HEAD), e com isso descarta (perde) as mudanças locais   
para esta funcionalidade, atualmente pode se usar `git restore`

### `git checkout -b`
cria uma nova branch e já muda para ela     
para esta funcionalidade, atualmente pode se usar `git switch -c`

---

## `git clone`
clona um repositório remoto existente para um diretório local, que será então um novo repositório local   
por tratar-se de um clone de um repositório já existente, não é necessário inicializar como um repositório (`git init`) e nem especificar a origin (`git remote add origin`), pois estes passos já virão prontamente configurados

---

## `git commit`
um "commit" é a inserção de um conjunto de alterações no histórico do repositório   
a princípio ocorre no repositório local, e depois precisa ser sincronizado com o repositório remoto

### `git commit -m`
para poder realizar o commit, é necessária uma "mensagem", um pequeno texto que registra ou descreve as alterações referentes ao commit, a qual é inserida após esta opção  
é possível pular duas linhas e depois escrever "Co-authored-by:" seguido de nome e e-mail, antes de fechar aspas, para especificar co-autoria

### `git commit --ammend`
permite fazer alterações no último commit feito, como alterar a mensagem ou adicionar arquivos esquecidos

---

## `git config`
configurações como nome de usuário e e-mail, necessárias para atestar autoria de código

### `git config --global`
aplica as configurações para todo o sistema, e não apenas para o repositório atual

---

## `git diff`
mostra as diferenças entre os estados atuais dos arquivos e aqueles no último commit sincronizado

### `git diff --staged`
compara as alterações no stage com o último commit sincronizado

### `git diff --color`
mostra as diferenças em formato mais legível e "amigável"

---

## `git fetch`
coleta as atualizações do repositório remoto, como novos commits e novas branches, mas não mescla automaticamente ao estado do repositório local atual (quem faz isso é o `git pull`)   
assim, permite que se decida por mesclar ou não (em caso positivo, parte-se para `git merge` ou `git rebase`)

---

## `git init`
converte o diretório atual em um repositório git

---

## `git log`
exibe um log com todos os commits na branch atual do repositório

### `git log --all`
exibe um log com os commits de todas as branches

### `git log --decorate`
exibe os logs decorados com nomes de branches e tags

### `git log --format` ou `git log --pretty`
permite especificar quais colunas de informações mostrar ao exibir os logs

### `git log --graph`
exibe os commits em formato de árvore

### `git log --oneline`
exibe os commits de forma resumida a um por linha

### `git log -p`
exibe o histórico de commits como o `git log` tradicional, mas acrescenta alterações detalhadas (com o formato de diffs) feitas em cada commit

---

## `git merge`
mescla uma branch especificada à branch atual   
se não houver conflitos, é automático   
se houver, é necessário resolvê-los antes   
o comando cria um tipo de commit especial, mostrando o ponto onde os históricos das diferentes branches se unem e passam a ser um só

---

## `git pull`
"puxa" alterações do repositório remoto para o repositório local

---

## `git push`
"empurra" os commits presentes no repositório atual para o repositório remoto

### `git push -u` ou `git push --set-upstream`
"empurra" os commits enquanto cria uma associação entre o repositório local e o repositório remoto  
tipicamente, usa-se `git push -u origin main` para associar a branch padrão "main" à origin previamente configurada  
feita esta associação, pode-se economizar tempo posteriormente ao usar `git pull` e `git push`, pois não será necessário especificar a branch toda vez

### `git push origin :`
excepcionalmente, não tem a ver (apenas) com "empurrar" alterações
esses dois pontos são seguidos do nome de uma branch que se deseja deletar no repositório remoto    
é bom lembrar que "origin" é um apelido padrão para repositório remoto, usado por convenção, e não obrigatório

---

## `git rebase`
re-baseia a branch atual em uma outra branch especificada  
em outras palavras, copia todo o histórico de uma branch especificada para antes do histórico da branch atual   
é semelhante a `git merge`, pois de certa forma também mescla duas branches, mas seu funcionamento é diferente e reescreve histórico, exigindo cuidado

---

## `git remote`
administra repositórios remotos associados ao repositório local

### `git remote add`
adiciona um repositório remoto a ser associado ao repositório local     
tipicamente, usa-se `git remote add origin`, seguido do endereço do repositório em HTTPS ou SSH     
"origin" é o nome padrão, por convenção, mas não é obrigatório

### `git remote remove`
remove um repositório remoto da lista de associações ao repositório local atual

### `git remote rename`
renomeia o "apelido" de um repositório remoto, por exemplo caso se quisesse mudar de "origin" para "origem" ou qualquer outra coisa

### `git remote set-url`
altera/atualiza a URL de um determinado repositório remoto

### `git remote -v`
permite visualizar uma lista dos repositórios remotos vinculados ao repositório local atual

---

## `git reset`
desfaz commits e pode modificar o histórico de maneiras poderosas (e portanto, perigosas)   
é importante notar que, diferentemente do `git revert`, é usado seguido do hash do commit a que se deseja retornar, e não de algum dos que se deseja desfazer

### `git reset --soft`
desfaz commits, mas mantém as alterações no stage (preparadas para um novo commit)

### `git reset --mixed`
é a opção padrão    
desfaz commits e limpa o stage, mas mantém as alterações no diretório de trabalho, para que se possa decidir o que fazer com elas

### `git reset --hard`
desfaz commits, e limpa o stage e o diretório de trabalho
é portanto a opção mais perigosa, usar com cuidado

---

## `git restore`
restaura arquivos para o estado do último commit    
em outras palavras, desfaz alterações e deleções

### `git restore --staged`
retira arquivos do "stage", funciona como um "unstage"

### `git restore --source`
utiliza o hash de um commit específico, e depois o nome de um ou mais arquivos que se deseja restaurar, para seus estados no referido commit

---

## `git revert`
é usado seguido do hash de um commit específico para reverter o mesmo   
cria um novo commit que desfaz as alterações feitas no commit especificado

---

## `git rm`
remove arquivos do repositório local e também marca a remoção para o próximo commit     
ou seja, deleta o arquivo do projeto e registra no git que ele deve ser removido no repositório

### `git rm --cached`
remove só do git, mas não do diretório  
usado para tirar arquivos do controle de versão, sem deletar do disco

---

## `git show`
é usado seguido do hash de um commit, para mostrar todas as alterações feitas no mesmo  
é semelhante ao `git log -p`, mas funciona para um commit específico, não para o log todo

---

## `git stash`
"guarda pra depois" as alterações feitas    
útil caso o trabalho seja interrompido por alguma demanda prioritária e imprevista, por exemplo

### `git stash apply`
re-aplica as alterações guardadas na stash, especificadas pelo índice que segue o comando   
lembrando que estes índices podem ser consultados com `git stash list`  
este comando não remove as alterações re-aplicadas da stash

### `git stash clear`
limpa toda a stash

### `git stash drop`
descarta alterações guardadas na stash, especificadas pelo índice que segue o comando   
lembrando que estes índices podem ser consultados com `git stash list`  
se for usado sem especificar um índice, descarta as últimas alterações empilhadas

### `git stash list`
exibe uma lista com as alterações guardadas na stash

### `git stash pop`
re-aplica alterações guardadas na stash, especificadas pelo índice que segue o comando  
lembrando que estes índices podem ser consultados com `git stash list`  
este comando remove as alterações re-aplicadas da stash     
se for usado sem especificar um índice, re-aplica as últimas alterações empilhadas

### `git stash push -m`
"empurra" alterações para a stash com uma mensagem, parecendo um commit, para fins de clareza

---

## `git status`
exibe diferentes informações sobre o estado atual do repositório local e em relação ao repositório remoto

---

## `git switch`
muda para uma branch especificada

### `git switch -c`
"create"    
cria uma nova branch e já muda para ela

### `git switch -f`
"force"     
força a troca de branch, sobrescrevendo alterações locais