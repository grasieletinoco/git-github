# Introdução ao Git e GitHub

### Git e GitHub para iniciantes. Guia para aprender a versionar do zero




### O que é Git?<br />

É um sistema de controle de versão distribuído. Ele é um projeto de código aberto desenvolvido em 2005 por Linus Torvalds (o criador do Linux).


### Comandos Básicos

<code>git help</code> : Ajuda <br />
<code>git init</code> : Cria um repositório <br />
<code>git add *</code> : Adiciona arquivos <br />
<code>git status</code> : Verifica status dos arquivos <br />
<code>git commit</code> : Comitar arquivos <br />
<code>git commit -m "Mensagem"</code> : Comitar arquivos <br />
<code>git rm</code> : Remove arquivos <br />
<code>git mv</code> : Move arquivos <br />
<code>git log</code> : Visualizar logs <br />
<code>git remote -v</code> : Lista o link dos seus repositórios remotos <br />
<code>git remote add origin LINK DO GITHUB</code> : Vincular repositório local com um repositório remoto <br />
<code>git remote show origin</code> : Exibe informações dos repositórios remotos <br />
<code>git push origin master</code> : Para "empurrar" o codigo para Github <br />
<code>git pull origin master</code> : Para "puxar" o codigo do Github <br />
<code>git clone URL</code> : Clonar um repositório <br />
<code>ls</code> : Listar <br />
<code>ls -a</code> : Listar arquivos ocultos <br />
<code>cd NOME</code> : Navegar na pasta <br />
<code>cd ..</code> : Retroceder um nível <br />
<code>mkdir NOME-ARQUIVO</code> : Criar pasta <br />
<code>ctrl + l</code> : Limpar tela do terminal <br />


### Instalando e Configurando o Git

1. Download da versão Git para Windows  https://git-scm.com/download/win
2. Após a instalação, a primeira coisa que você deve fazer é definir o seu nome de usuário e endereço de e-mail. Digite esses comandos abaixo
   <code>git config --global user.name "Nome"</code>
   <code>git config --global user.email nome@example.com</code>
3. Você só precisará fazer isso uma vez 


#### Como Funciona o Git por Baixo dos Panos

O Git usa diferentes tipos de objetos para armazenar informações do repositório. Esses objetos são principalmente de 4 tipos: blob, tree, commit e tag. O Git faz referência a quase todas as informações armazenadas por meio de um hash. Ele usa um hash SHA-1 que é uma string de 40 caracteres.

- SHA1: Secure Hash Algorithm (Algoritmo de Hash Seguro). É uma função de dispersão criptográfica (ou função hash criptográfica). Foi criado pela NSA. Utiliza criptografia com hash de 40 caracteres
- Objetos Internos do Git 

1. Blobs (É o tipo de objeto usado para armazenar o conteúdo de cada arquivo em um repositório. Um blob não registra sua data de criação, seu nome ou nada além de seu conteúdo. Cada blob é dentificado por seu hash SHA-1)
2. Trees (Uma árvore é basicamente uma lista de diretórios. Possui vários ponteiros para blobs e outras árvores, além de fornecer o modo, tipo de objeto e um nome para o arquivo ou diretório. Também são identificadas por seus hashes SHA-1. )
3. Commits (Conecta todos os outros objetos juntos. Aponta para uma única árvore. Ele contém meta-informações sobre aquele ponto no tempo, como um carimbo de data/hora, o autor das alterações desde o último commit)
4. Tag (É uma maneira de marcar um commit específico como especial de alguma forma. Normalmente é usado para marcar certos commits como lançamentos específicos ou algo nesse sentido.


### Ciclo de Vida dos Arquivos

-Untracked e Tracked (Unmodified, Modified, Staged)
Cada arquivo em seu diretório de trabalho pode estar em um dos dois estados: Untracked e Tracked

1. Untracked (Arquivos não rastreados. Esses arquivos nunca foram adicionados ao repositório Git ou foram removidos do repositório.)
2. Tracked (Arquivos rastreados. Esses arquivos foram adicionados ao repositório. O Git tem três estados principais que seus arquivos podem estar: Unmodified que é um arquivo que não sofreu mudanças, Modified que trata de um arquivo que sofreu mudanças e Staged que é um arquivo preparado para comitar

- Ambiente de Desenvolvimento (Working Directory, Staging Area, Local Repository)

1. Working Directory (É a área onde você está trabalhando atualmente. É onde seus arquivos vivem)
2. Staging Area (É quando o git começa a rastrear e salvar as alterações que ocorrem nos arquivos)
3. Git Directory (É tudo em seu diretório, ou seja, a área onde salva tudo)


### O que é GitHub?

O Github é um repositório remoto, criado como um serviço online de hospedagem de repositórios do Git.


### Criando Conta no GitHub 

Acesse a página https://github.com/ e siga as instruções para criar a conta


### Criando um Commit e Subindo um Repositório

1. Abra o Git Bash e crie uma pasta digitando <code>mkdir NOME-DA-PASTA</code> e dê enter. 
2. Para entrar na pasta criada digite <code>cd NOME-DA-PASTA</code> 
3. Agora para criar o repositório digite <code>git init</code> e dê enter.
4. Crie um arquivo utilizando seu editor de texto e salve em .md (nomedoarquivo.md)
5. Use o comando <code>git add *</code> para adicionar o arquivo e dê enter
6. Para comitar use o comando <code>git commit -m "MENSAGEM"</code> e dê enter
7. Agora para subir o Repositório acesse o GitHub e clique em novo repositório e copie endereço/url gerada na opção “push an existing repository from the command line”
8. Abra o Git Bash onde está o seu projeto e use o comando <code>git remote add origin LINK DO GITHUB</code> para vincular o repositório local com o remoto
   9 - Depois use o comando <code>git remote -v</code> para listar o link
   10 - E por último use o comando <code>git push origin master</code> para "empurrar" o codigo para o Github


### Clonando Repositórios 

1. Acesse a página do repositório que deseja clonar e copie a url do repositório
2. Depois abra Git Bash
3. Agora digite o seguinte comando: <code>git clone</code> e a URL já copiada. Como nesse exemplo git clone https://github.com/USUARIO/REPOSITORIO.git 
4. Pressione enter para criar seu clone local. 


### Resolvendo Possíveis Conflitos

1. Os conflitos são causados quando aconteçe duas ou mais alterações diferentes na mesma linha do mesmo arquivo e o git não sabe qual das alterações manter.
2. Para resolver o conflito é preciso alterar o arquivo para que contenha apenas uma versão.
3. Abra o arquivo, exclua os marcadores de conflito `<<<<<<<`, `=======`, `>>>>>>>` e faça as alterações desejadas
4. Para finalizar, após as correções, iremos usar o comando <code>git add *</code> para adicionar  o arquivo, depois um <code>git commit -m "MENSAGEM"</code> para comitar o arquivo e então, <code>git push origin master</code> para mandar para o repositório remoto.
