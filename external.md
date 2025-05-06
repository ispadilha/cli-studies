# Comandos de terminal não nativos do Sistema Operacional

_Estes programas não vêm instalados juntamente ao SO e isso precisa ser feito manualmente. São oriundos de terceiros e da comunidade em geral. Foram estudados em Ubuntu, talvez não sejam compatíveis com alguns outros SOs, e nestes casos existam alternativas._

---

# `gh`
"github"    
interface de linha de comando para o github  
permite criar e gerenciar repositórios, pull requests, issues, releases, gists, etc   
integra-se com o git e pode ser usado em qualquer repositório git

---

## `gh auth`
"authenticate"  
lida com autenticação de conta no github

### `gh auth login`
faz login, e consequentemente autentica, um usuário com sua conta do github

### `gh auth logout`
faz logout da conta do github que estiver autenticada   
é bom lembrar que isto foi útil (e necessário) quando, ao mudar a senha do github, a autenticação guardada no sistema "quebrou"

### `gh auth status`
exibe informações sobre a autenticação atual    
é importante se atentar a questões de segurança, como tokens guardados fora de keyring (nesse caso seriam legíveis) ou chaves SSH sem senha     
os dois casos acima são problemáticos se a máquina for comprometida

---

## `htop`
"human-friendly top processes"    
semelhante ao comando `top` nativo, lista os processos no "topo" de uso dos recursos do sistema   
é uma versão "modernizada" ou mais "amigável" quanto a sua interface gráfica    

---

## `telnet`
estabelece uma conexão de terminal remoto com outro computador  
permite interagir diretamente com serviços em execução em portas específicas de outro host  
cria conexões TCP (porta 23 por padrão)     
o comando aceita um domínio e uma porta     
é usado para teste, diagnóstico, depuração, exploração manual de protocolos baseados em texto (como HTTP, SMTP, POP3)    
é importante saber que não criptografa os dados     
ao executar, abre um modo interativo no qual se pode escrever requisições manualmente