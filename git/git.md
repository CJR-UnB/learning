# GIT

O Git é uma ferramenta que você usará em, provavelmente, todos os seus projetos. O entendimento total deste guia será crucial para que você não perca tempo com a manipulação de arquivos quando estiver desenvolvendo seu projeto.

## O que é Git?

Git é um sistema de **versionamento** de arquivos. Com a ajuda desta ferramenta, várias pessoas podem trabalhar em um projeto simultaneamente sem se preocupar com a perda de conteúdo. Desta forma, o desenvolvimento do projeto é muito mais fácil e rápido.

## O que é Github?

Github é um serviço web que tem várias outras funcionalidades complementares ao Git. Nele você pode hospedar seus projetos, conhecer os projetos de outras pessoas e visualizar cada etapa (ou versão) de um projeto *open source* no qual você também pode colaborar.

## Repositórios

Quando você quer criar um projeto, você cria um **repositório** no GitHub. O repositório será basicamente o depósito de todos os arquivos do seu projeto. Se você é um desenvolvedor e seu gerente já criou um repositório, você deverá clonar esse repositório para que você possa trabalhar nele. Quando terminar de desenvolver uma funcionalidade do projeto, você enviará seus arquivos para o repositório para que toda a equipe possa ver o que você fez.

## Branches

Uma das funcionalidades mais importantes do Git são as **branches**. Em português, ramificação. Pense que você quer escrever uma carta em um papel especial. Como você não quer rasurar o papel especial caso você queira mudar o texto da carta, você fará vários rascunhos antes de passar o texto para o papel especial. E como é uma carta para a pessoa amada, cada parágrafo deve estar perfeito antes de escrevê-lo no papel especial. 

![Mail](/images/mail.gif)

Quando você cria um repositório, automaticamente é criado uma branch padrão chamada **master**. Seguindo nosso exemplo, a master é o papel especial. Você não ~~quer~~ deve trabalhar diretamente na master. Para isso você cria um rascunho, uma nova branch, normalmente chamada de **develop**. Essa branch é seu rascunho principal e quando você estiver satisfeito com o trabalho que fez nele, você poderá passar o texto (arquivos) para o papel especial (master). Como a carta será enviada à pessoa amada, cada parágrafo tem que ser trabalhado antes de ser colocado no rascunho principal (develop). Neste caso, o parágrafo está para o texto assim como uma funcionalidade do projeto está para o projeto inteiro. Assim, temos as branches chamadas de **features**. Digamos que você queira fazer uma página de introdução do projeto. Terá, então, que criar uma feature para isso. Um nome apropriado para ela seria `feature_intro`. O comando para manipular branches é o `checkout`.

```shell

$ git checkout -b feature_intro
Switched to a new branch 'feature_intro'

```
Será nessa feature que você trabalhará. Quando estiver satisfeito com o trabalho que fez, passará o seu parágrafo (feature) para o rascunho principal (develop). Falaremos mais sobre como é esse processo mais adiante.

## Commits

Outra funcionalidade essencial ao Git são os **commits**. Sigamos o seguinte exemplo: você é o dono de uma fábrica de automóveis e compra uma máquina de montagem alemã. Enviar a máquina inteira de uma vez é irrealizável, logo ela será enviada em diversos *pacotes* que juntos formarão a máquina inteira. Cada pacote terá peças, parafusos, manuais, etc. O Git funciona da mesma forma: a feature é a máquina de montagem alemã, os pacotes são os commits e as peças são os arquivos.

Para adicionar os arquivos aos pacotes usamos o comando `add`.

```shell

$ git add -A

```
O `-A` significa *all*. Ao invés de `-A`, podemos usar `--all` e `.`.

Assim como os pacotes da máquina de montagem, os commits tem mensagens explicando o que tem dentro. Quando você for realizar um commit (após adicionar os arquivos do pacote), escreverá uma pequena mensagem explicando o que aqueles arquivos fazem. Por exemplo: 

```shell

$ git commit -m 'Peças do motor da máquina'

``` 
O `-m` ali significa *message*. 

![Repository Diagram](/images/repositorydiagram.png)

## Git Merge

Agora você já sabe o que são **branches** e **commits**. Podemos começar a misturar tudo isso, pois é assim que funciona no Git. 

Voltemos ao exemplo da carta à pessoa amada. Você está fazendo a introdução da sua carta (`feature_intro`) e está satisfeito com as frases que formulou (arquivos) e que "enviou" ao rascunho da introdução (`commits`). Como você é um pouco desajeitado, tem medo de perder algum papel com todos esses rascunhos. Então você repassa a introdução (`feature_intro`) para o rascunho principal (`develop`). Fazer isso quando está realmente escrevendo é simples. No Git também é!

O que temos que fazer? Dar `merge` na develop. Primeiro, você passa para a develop:

```shell

$ git checkout develop
Switched to branch 'develop'

``` 

Agora você pode juntar todo o trabalho que fez na `feature_intro` para a `develop`.

```shell

$ git merge feature_intro
Updating db9676f..574fd91
Fast-forward
  primeira_frase.txt 						| 3 +
  segunda_frase.txt 						| 2 +
  terceira_frase.txt 						| 3 +
3 files changed, 8 insertions(+), 0 deletions(-)

```

Como você está satisfeito com a introdução, não precisa ficar guardando um monte de papel, portanto nada mais natural do que jogá-lo fora. No Git é a mesma coisa: vamos deletar a branch `feature_intro`.

```shell

$ git branch -d feature_intro
Deleted branch feature_intro (was 67f1319).
$ git branch
* develop
  master

``` 

Pronto! Agora você sabe como usar o `merge`!

## Git Ignore

Quando estiver trabalhando no seu projeto, as vezes você desejará deixar alguns arquivos fora do escopo do Git para que ele não os atualize toda hora que for fazer uma alteração no projeto. Mas que arquivos seriam esses? Arquivos referentes à base de dados que está no seu computador são um exemplo disso. Como o projeto ainda não tem um servidor próprio, cada desenvolvedor tem seu banco de dados. Não há necessidade de ficar enviando esse arquivo e alterando-o toda vez que for trabalhar na sua máquina.

### Bibliografia e sites úteis

[Introdução ao Git](http://tableless.com.br/tudo-que-voce-queria-saber-sobre-git-e-github-mas-tinha-vergonha-de-perguntar/) | Esse guia é muito didático e muito bom! O autor deste artigo recomenda esse link. <br/>
[GitHub Guides](https://guides.github.com/) | Guias do próprio GitHub sobre o GitHub!<br/>
[Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/) | Guias básicos e avançados de Git.<br/>
[Git Ignore](https://help.github.com/articles/ignoring-files/) | Saiba mais sobre o Git Ignore.<br/>