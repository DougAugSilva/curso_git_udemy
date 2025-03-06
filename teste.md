# Curso Git e Github Udemy

## Comandos Git

- **git init**: Inicia uma nova seção no git e/ou cria um repositório.

- **git status**: nos dá o status dos arquivos para com o repoitório no servidor.

- **git add** : adiciona arquivos

- **git commit -m**: deixa os aqrquivos prontos para o envio

- **git push**: envia os arquivos ao servidor, atualizando o código

- **git pull**: Faz uma busca por atualizações do código no servido, 
se encontradas, elas são inseridas ao código atual existente em nossa maquina.

- **git clone**: Este comando clona um repositório, baizando ele de um servidor remoto.
Este comando é utilizado quando entramos em um novo projeto, por exemplo.

- **git rm**: Deleta o arquivo por meio da remoção dele da monitoração do git. Depois de remover o arquivo, é necessário
dar um *comi* para avisar a equipe da remoção, e depois um push para deletalo no repositório.

- **git log**: Nos dá um histórico de alterações do projeto. Pra sair do log aperque "q".

- **git mv**: Permite mover arquivos para outras pastas dentro do repositório. Podendo também ser utilizado para renomear arquivos, fazemos isso por mover o arquivo para a mesma pasta, mas alterando seu nome.

- **git checkout**: Desfaz uma alteração feita em um arquivo, fazendo este voltar ao seu estado original.

## Ignorando Arquivos e Diretórios no Projeto
Para ignorarmos arquivos no projeto, criamos um arquivo **.gitignore** na pasta de nosso projeto e especificamos dentro dela os arquivos que devem ser ignorados, isto é, não devem ser enviados para o servidor junto com os comits. 

## Desfazendo Todas as Alterações
Como o comando **git reset** podemos resetar todas as mudanlças feitas na branch atual, inclusive as já comitadas. Geralmente ele é utilizado com a flag **--hard**. Temos também que colocar a branch na qual queremos ficar pareados, geralmente é a main. Sua sintaxe é **git reset --hard "branch para parear"**

## Trabalhando com Branches
Branchs separam versões do projeto, quando o prokjeto é criado ele se inicia com a branch main (ou master). Gralmente uma nova feature de um projeto fica em uma branch separada. Após as alterações na brach serem finalizadas, os branchs são unidos a master para termos o código-fonte final.

### Criando Branches
 Os seguintes comandos são muito utilizados no dia a dia de um desenvolvedor para se lidar com as branches.

 - **git branch**: Visualiza as branches disponiveis.

 - **git branch <"nome da branch">**: Cria uma nova branch no projeto.

 