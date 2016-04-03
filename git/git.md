# GIT

O Git é uma ferramenta que você usará em, provavelmente, todos os seus projetos. O entendimento total deste guia será crucial para que você não perca tempo com a manipulação de arquivos quando estiver desenvolvendo seu projeto.

## O que é Git?

Git é um sistema de **versionamento** de arquivos. Com a ajuda desta ferramenta, várias pessoas podem trabalhar em um projeto simultaneamente sem se preocupar com a perda de conteúdo. Desta forma, o desenvolvimento do projeto é muito mais fácil e rápida.

## O que é Github?

Github é um serviço web que tem várias outras funcionalidades complementares ao Git. Nele você pode hospedar seus projetos, conhecer os projetos de outras pessoas e visualizar cada etapa (ou versão) de um projeto *open source* no qual você também pode colaborar.

## Repositórios

Quando você quer criar um projeto, você cria um **repositório** no GitHub. O repositório será basicamente o depósito de todos os arquivos do seu projeto. Se você é um desenvolvedor e seu gerente já criou um repositório, você deverá clonar esse repositório para que você possa trabalhar nele. Quando terminar de desenvolver uma funcionalidade do projeto, você enviará seus arquivos para o repositório para que toda a equipe possa ver o que você fez.

## Branches

Uma das funcionalidades mais importantes do Git são as **branches**. Em português, ramificação. Pense que você quer escrever uma carta em um papel especial. Como você não quer rasurar o papel especial caso você queira mudar o texto da carta, você fará vários rascunhos antes de passar o texto para o papel especial. E como é uma carta para a pessoa amada, cada parágrafo deve estar perfeito antes de escrevê-lo no papel especial. 

![Mail](/images/mail.gif)

Quando você cria um repositório, automaticamente é criado uma branch padrão chamada **master**. Seguindo nosso exemplo, a master é o papel especial. Você não ~~quer~~ deve trabalhar diretamente na master. Para isso você cria um rascunho, uma nova branch, normalmente chamada de **develop**. Essa branch é seu rascunho principal e quando você estiver satisfeito com o trabalho que fez nele, você poderá passar o texto (arquivos) para o papel especial (master). Como a carta será enviada à pessoa amada, cada parágrafo tem que ser trabalhado antes de ser colocado no rascunho principal (develop). Neste caso, o parágrafo está para o texto assim como uma funcionalidade do projeto está para o projeto inteiro. Assim, temos as branches chamadas de **features**. Digamos que você queira fazer uma página de introdução do projeto. Terá, então, que criar uma feature para isso. Um nome apropriado para ela seria `feature_intro`. E será nessa feature que você trabalhará. Quando estiver satisfeito com o trabalho que fez, passará o seu parágrafo (feature) para o rascunho principal (develop).

## Commits

Outra funcionalidade essencial ao Git são os **commits**. Sigamos o seguinte exemplo: você é o dono de uma fábrica de automóveis e compra uma máquina de montagem alemã. Enviar a máquina inteira de uma vez é irrealizável, logo ela será enviada em diversos *pacotes* que juntos formarão a máquina inteira. Cada pacote terá peças, parafusos, manuais, etc. O Git funciona da mesma forma: a feature é a máquina de montagem, os pacotes são os commits e as peças são os arquivos. Assim como os pacotes, os commits tem mensagens explicando o que tem dentro. Quando você for realizar um commit, escreverá uma pequena mensagem explicando o que aqueles arquivos fazem. Por exemplo: `git commit -m 'Peças do motor da máquina'`. O `-m` ali significa *message*. 

![Repository Diagram](/images/repositorydiagram.png)

## Git Ignore

Quando estiver trabalhando no seu projeto, as vezes você desejará deixar alguns arquivos fora do escopo do Git para que ele não os atualize toda hora que for fazer uma alteração no projeto. Mas que arquivos seriam esses? Arquivos referentes à base de dados que está no seu computador são um exemplo disso. Como o projeto ainda não tem um servidor próprio, cada desenvolvedor tem seu banco de dados. Não há necessidade de ficar enviando esse arquivo e alterando-o toda vez que for trabalhar na sua máquina.





### Bibliografia e sites úteis

[Introduction to Git](https://www.drupal.org/node/991716) <br/>
[Introdução ao Git](http://tableless.com.br/tudo-que-voce-queria-saber-sobre-git-e-github-mas-tinha-vergonha-de-perguntar/) <br/>
[GitHub Guides](https://guides.github.com/) <br/>
[Atlassian Git Tutorial](https://www.atlassian.com/git/tutorials/) <br/>
[Git Ignore](https://help.github.com/articles/ignoring-files/) <br/>