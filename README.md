# Como usar o Git e Github na prática
 

## Instalando o GIT

[Neste link](https://git-scm.com/downloads) encontramos os arquivos para download das versões do `Git` para Windows, Linux e MacOS.

## Softwares úteis

Também é interessante instalar o [Visual Studio Code](https://code.visualstudio.com/). Com ele podemos escrever e editar código em várias linguagens, como `Markdown`, `Python`, `HTML`, `CSS`, etc.

## Como criar um novo projeto

* Crie uma nova pasta no em seu computador

* Dentro desta pasta, clique com o botão direito do mouse e selecione _Abrir com Code_

* Escreva um novo arquivo e nomei-o `README.md`, sendo `md` a extensão para arquivos do tipo `Markdown`

* Neste arquivo nomeado README, escreva a respeito do projeto que está sendo desenvolvido

* Salve o arquivo

Agora, com o primeiro arquivo pronto e salvo, é hora de usarmos o Git:

* Novamente, dentro da pasta, clique com o botão direito do mouse e selecione _Git Bash Here_

* Agora, na linha de comando do _bash_, digite `git init` para inicializar o repositório

Após o comando acima, é criada uma pasta `.git` dentro da pasta do projeto. Contudo, o arquivo `README.md` ainda não foi salvo no repositório do Git. Para isso, devemos passar o arquivo da pasta (_working directory_) para a área de stage (_staging area_), o que é feito com o comando `git add README.md`. Somente os arquivos na _stanging area_ podem ser enviados ao repositório (_repository_), o que é feito com o comando `git commit`. Na figura abaixo vemos como funciona o processo para que seja possível "comprometer-se" (_commit_) com uma mudança.

<img src="https://i1.wp.com/www.markus-gattol.name/misc/mm/si/content/git_git_add.png">

Devemos, então, seguir os seguintes passos:

* `git add README.md` para colocar o arquivo na _staging area_ 

***OBS: se tivermos modificado mais de um arquivo, podemos usar o comando `git add .`***

* `git commit -m "primeiro commit"` para, de fato, enviar o arquivo para o repositório

***OBS: o `-m` no comando acima é uma tag para mensagem. Logo, o que escrevemos entre aspas é uma mensagem que, preferencialmente, deve indicar as mudanças feitas neste `commit`.***

## Links úteis
[Documentação do Git](https://git-scm.com/doc)

[Documentação Markdown](https://www.markdownguide.org/)


## Repositório no GitHub

O `GitHub` é uma plataforma de hospedagem de código-fonte e arquivos com controle de versão usando o Git. Ele permite que programadores, utilitários ou qualquer usuário cadastrado na plataforma contribuam em projetos privados e/ou Open Source de qualquer lugar do mundo [Wikipédia](https://pt.wikipedia.org/wiki/GitHub)

Ainda, o `GitHub` pode ser visto como um tipo de "rede social para programadores", visto que lá é possível seguir pessoas, compartilhar código, receber e enviar sugestões de alteração em códigos, etc.

O próximo passo, agora, é criar uma conta no `GitHub`. Feito isso, então

* Já em seu perfil, selecione a aba **Repositories**

* A direita na tela você verá um botão verde escrito **New**, clique  

<img src="img\img01.png">
 
* Preencha as informações do projeto, como o nome e uma breve descrição

<img src="img\img02.png">

* Veja que também é possível determinar se o repositório será _public_ ou _private_, isto é, se estará disponivel para visualização de todos que entrarem em seu perfil ou apenas para você

* Depois de preencher as informações do projeto, clique em **Create repository** 

<img src="img\img03.png">

Após clicar em **Create repository**, a próxima página do `GitHub` já nos traz todos os comandos necessários para criar ou "empurrar" (_push_) repositórios.

<img src="img\img04.png">

No nosso caso, já temos um arquivo em nosso computador, o `README.md`, e temos que enviá-lo ao servidor remoto (`remote`), que é o `GitHub`

* Para isso, basta passar o endereço do repositório na plataforma do Github, usando o comando `git remote add origin <link do repositório>`

* `origin` é o nome utilizado para referenciar o nosso repositório remoto

Agora já temos o nosso repositório local conectado com o respositório do Github, porém o `commit` que damos na máquina não sobe automaticamente para a plataforma

* Para isso, precisaremos empurrar para lá com o `git push -u origin main`

Agora, ao recarregarmos a página veremos o nosso arquivo aqui na plataforma!

## Alterando e adicionando arquivo

Agora que temos o nosso repositório no Github configurado corretamente, podemos utilizá-lo para criar novas versões dos nossos arquivos.

Sempre que alterarmos, ou acrescentarmos, algo em nosso diretório local, devemos seguir as seguintes etapas

* Enviar para a _staging area_ com o `git add <nome do arquivo>`

* "Comprometer-se" com a alteração com o `git commit -m "descrição da alteração"`

* E, para que a alteração siga para o nosso respositório do Github precisamos dar o _push_, `git push origin main` 

Se olharmos agora o nosso código no Github, ele terá sido alterado, e não só isso, se clicarmos no nome do `commit`, podemos ver exatamente as alterações que foram feitas nele.
O verde com `+` e o vermelho com `-` mostra, os conteúdos que foram adicionados e editados dentro do código.

## Pull

E se a alteração for feita no repositório remoto, como sincronizar com o repositório local?

* Basta executar o comando `git pull`, ele irá puxar todas as alterações feitas no repositório do Github para o seu repositório local

## Clone

Como dito anteriormente, o `GitHub` permite que tenhamos acesso aos códigos escritos por outros programadores. Mas, como baixar um arquivo do `GitHub` de outra pessoa para o seu repositório local?

* Basta usar o comando `git clone <link do repositório>`