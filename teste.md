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

### Criando e Manipulando Branches
 Os seguintes comandos são muito utilizados no dia a dia de um desenvolvedor para se lidar com as branches.

 - **git branch**: Visualiza as branches disponiveis.

 - **git branch "nome da branch"**: Cria uma nova branch no projeto.

 - **-d** ou **--delete**: Utuilizado para deletar branchs por medidas de organização, ou foram criados errados. Sua sintaxe é *git -d "nome da branch"*.

 - **git checkout -b "nome da branch**: É utilizada para mudarmos para outra branch. Tome cuidado, alterar de branch pode levar os arquivos que não foram comitadados junto, sendo que eles vão para o novo branch e não ficam no anterior.
 A tag *-b* alem de mudar, cria no novo branch.

 - **git merge "nome da branch**: Faz a união da branch artual com uma branch especifica, ganhando assim as funcionalidades dela.

 **OBS**: Geralmente sempre utilize o *merge* para atualizar a sua branch com relação a master, e nunca ao contrário. O envio de funcionalidades para a master se dará no módulo sobre GitHub.

 ### Trabalhando com o Git Stash
 A *Stash* funciona como se fosse a *lixeira* do git, podemos mandar branches para ela e recuperalas depois se necessario

 - **git stash**: Deleta nossa brach toda e volta ó código para o estado da branch anterior.

 - **git stash list**: Lista os elementos presentes na stash, numerados de 0 em diante.

 - **git stash aply "numero do item na stash"**: Recupera um elemento específico da stash.

- **git stash show -p "numero da stash"**: Mostra quais alterações forma feitas pela aquela stash.

- **git stash clear**: Limpa nossa stash deletando todos os itens.

- **git stash drop "nome do item"**: Deleta um item especifico da stash.

### Utilizando Tags no Git
A tag é diferente da stash, uma tag serve de cheackpoint de uma branch, sendo utilizada para demarcar estágios do desenvolvimento de algum recurso.

- **git tag -a "nome da tag" -m "mensagem"**: Cria uma tag em uma brach.

- **git show "nome da tag"**: Podemos verificar os detalhes da tag.

- **git checkout "nome"**: Mudamos de uma tag para outra, deste modo é possivel retrocedermos ou avançarmnos em cheackpoints de uma branch.

**OBS**: Também podemos enviar tags para o repositório do servidor, para isso utilizamos os seguintes comandos.

- **git push origin "nome da tag"**: Compartilha uma tag para o repositório.

- **git push origin --tags**: Envia várias tags para o repoisitório.

- **git remote**: Mudamos a Url de origem do repositório, podendo assim mudarmos de seviço de ospedagem do repositório sem precisar fazer toda a clonagem deste. Por exemplo, mudar do GitHub para o Bitbucket.

  - **git remote -v**: Mostra quais são os repositórios de origem de recebimento e envio.

  - **git remote rm origin**: Remove as origens.

  - **git remote origin "link repositorio"**: Adiciona um repositório de origem.

### Diferenças git fetch e git pull
- **git pull**: Tenta mesclar automaticamente após buscar os commits. Ele é sensível ao contexto, então todos os commits puxados serão mesclados em seu branch ativo no momento. git pull mescla os commits automaticamente sem deixar você revisá-los primeiro. Se você não gerenciar seus branches cuidadosamente, poderá ter conflitos frequentes.

- **git fetch**: Reúne todos os commits do branch de destino que não existem no branch atual e os armazena em seu repositório local. No entanto, ele não os mescla com seu branch atual. Isso é particularmente útil se você precisa manter seu repositório atualizado, mas está trabalhando em algo que pode quebrar se você atualizar seus arquivos. Para integrar os commits em seu branch atual, você deve usar git merge depois.

### Submodulos no git
Podemos adicionar mais de um repositório em um projeto, suponha por exemplo que em uma empresa com varios setores, tenhamos um grande projeto com cada setor possuindo um repositório, podemos assim adicionar cada repositório como submódulo do projeto.

- **git submodule**: Verifica os submódulos do projeto.

- **git submodule add "link do repositório"**: Adiciona o novo repositório ao projeto como uma pasta. 

**OBS**: Para atualizarmos e trabalharmos com o submodulo, basta irmos até a pasta do submódulo com o comando *cd*, sendo que as atualizações vão para a origem deste submódulo.

- **git push --recurse-submodules=on-demand**: Atualiza as mudanças comitadas para o repositório de origem do submódulo.

## Análise e inspeção de repositórios

- **git show**: Ele nos da informações sobre o nosso branch atual, como por exemplo os comits. As modificações de arquivos entre os comits também serão exibidas.

- **git diff**: Quando utilizado as diferenças do branch atual com o remoto serão exibidas no terminal. Podemos também verificar a diferença entre arquivos com o **git diff "arquivo_a" "arquivo_b"**. 
Se colocarmos **git diff "branch especifica"**, verificamos a diferença só naquela branch para com o repositório.

**OBS**: Note que depois de um merge, se fizermos **git diff**, a diferença dos dois brancs será nenhuma.

- **git shortlog**: Nos dá um log resumido do projeto, sendo que cada commit se´ra exibido junto com o nome do autor. Podemos assim saber quais commits foram enviados ao projeto e por que.

## Administração de repositório

- **git clean -f**: Verifica e limpa todos os arquivos que não estão sendo trackeados, isto é, todos os arquivos que *não se utilizou o git add*.
É utilizado, por exemplo, para arquivos que são gerados automaticamente, e atrapalham assim a visualização do que é realmente importante.

- **git gc**: Abreviação de *garbage collector*, ele indentifica arquivos que não são mais necessários e os exclui, isso fará com que mais optimizado em questões de performance. Se recomenda utilizar pouco, por exemplo, uma vez no mês.

- **git fsck**: É uma abreviação de *File System Check*, esta função verifica a integridade de arquivos e suas conectividades, buscando assim possíveis corrupções de arquivos. É um comando de rotina assim como o git gc, utilizado para ver se está tudo certo com nossos arquivos.

- **git reflog**: Vai mapear todos os seus passos em um repositório, até uma mudança de branch é inserida neste log. Ele é diferente do *git log* que só armazena commits de uma branch.
Os reflogs ficam salvos até expirarem, o tempo de expiração padrão é de 30 dias.

**OBS**: Podemos nos mover dentro dos passos salvos pelo reaflog utilizando o comando reset, assim voltando o código a estados anterios e desfazendo erros, por exemplo.

- **git archive**: Transforma o repositório em um arquivo compacto, por exemplo, **git archive --format zip --output main_files.zip main**, trasforma a main em um arquivo zipado de nome *main_files.zip*.
