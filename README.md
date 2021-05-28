<h1 align="center">Manual de utilização do github</h1> 
<h4 align="center">🚀Tutorial de como usar o github de forma prática por linha de comando🚀</h4>

<p> 
O GIT é um software de versionamento de códigos, voltado a facilitar a gestão das versões, atualizações em scripts e o trabalho colaborativo.
	Sua lógica gira em torno de alterarmos um arquivo normalmente e então o adicionarmos, através de comandos, numa área pré-salvamento (git add) e salvar(git commit). A partir desse momento temos um commit, que é um ponto onde uma versão do projeto foi salva, como se fosse uma foto do código no momento 📸
  
  O GITHUB nada mais é do que o repositório web (ou plataforma, se preferir chamar assim) do mesmo repositório GIT em sua máquina local 😉
  
  Legal! Mas quero começar a usar isso logo, como faz !?
</p>

<h3>Vamos então aos pré-requisitos: </h3>
<p align="center">
 <a href="#cadastro_no_github">Cadastro no github</a> •
 <a href="#git_bash">GIT BASH</a>
</p>

<p>
   Antes de mais nada, crie sua conta na plataforma GITHUB. Para criar é bem simples, intuitivo e totalmente gratuito. Entre na área de login, click em sign up e siga preencha os dados necessários de sua preferencia.
   Agora precisamos do sotware GIT! Se você usa o Windows, recomendo baixar o [git bash](https://git-scm.com/download/win). Baixe o arquivo compatível com seu sistema e na instalação dê "next" e "aceito" padrões desse sistema operacional.
  Verifique se o GIT foi instalado corretamente! abra o CMD e digite o comando
  
```
git --version
```
 o resultados será algo semelhante a isso:
 ![image](https://user-images.githubusercontent.com/57183317/118011509-7fd92b00-b326-11eb-808a-db4adaeafd26.png)
 </p>
 
<h3>Configurando o GIT </h3>
<p>
	Para começar a usar o GIT em seu computador, você deve inserir suas credenciais (usuário e e-mail) para identifica-lo como autor do trabalho. O nome de usuário e e-mail devem corresponder aos do seu usuário no GITHUB.
	
Em seu shell, adicione seu nome:
```
git config --global user.name "seu_nome_de_usuario"
```
E seu email:
```
git config --global user.email "seu_email@exemplo.com"
```
Para checkar as configurações, digite:
```
git config --global --list
```

O argumento `--global` diz ao Git para sempre usar essas informações para qualquer coisa que você fizer em seu sistema. Se você omitir `--global` ou usar `--local`, a configuração será aplicada apenas ao repositório atual.
</p>

<h3>Comandos básicos do GIT/GIThub </h3>
<p>
Partiremos de um repositório criado no github! seja ele criado por você do zero ou por outros (que aliás é bem simples de criar, então dispensarei tutoriais sobre isso).

O primeiro passo é clonar o repositório remoto em sua máquina para começar a trabalhar com ele. Para clona-lo pegue o link http do repositório, igual na imagem abaixo

![image](https://user-images.githubusercontent.com/57183317/118031490-fa14aa00-b33c-11eb-828b-1f2e0fa532dd.png)

Agora rode o comando:
```
git clone <link_https>
```
e pronto! uma pasta com o mesmo nome do repositório aparecerá em sua máquina.

## Agora vamos falar sobre git add, git commit e git push (comece a internalizar na sua mente esses comandos, eles são essenciais hehe)

Repositório clonado! está na hora de botar as mãos na massa! Você já criou um script e uma subpasta "informacoes" com dois arquivos .txt e se pergunta "como faço pra usar o GIT/GIThub agora!?", simples jovem!
Abra seu Gitbash e vá até a pasta do seu repositório (você pode clicar com o botão direito numa parte em branco da pasta e selecionar "git bash here" ou navegar até o diretório através do comando `cd caminho/até/diretorio` )
Pronto!? agora use os comandos:
para adicionar o script:
```
git add nome_script
```
para adicionar a subpasta e todos seus arquivos:
```
git add informacoes/*
```
Agora os arquivos estão "pré-salvos", vamos salvá-los através do commit:

```
git commit -m "PALAVRA_CHAVE: descrição curta das alterações"
```
através desse comando, todas as alterações pré-salvas no comando git add serão salvas em um HEAD, que é como chamamos os "pontos onde as versões/commits são salvos". Agora vamos jogar essas alterações para o repositório remoto!

```
git push
```
Fim! simples assim! ao olhar o GITHUB você verá que ele já possui as alterações!

Outros dois comandos úteis são o status e pull. O comando pull seria o outro lado da moeda do push, o push atualiza o repositório web a partir do local e o pull atualiza o repositório local a partir do repositório web. 
- "Legal! Mas aí eu vou precisar ficar checando toda hora se tem algo diferente nos repositórios ?" -  claro que não, meu git-amigo! Para isso temos o comando status, ele faz uma varredura rápida de todas as diferenças no repositório web e local, ele nos diz se precisa fazer pull, se precisa fazer add e se precisa fazer commit :)
```
git pull
```
```
git status
```

#### Trabalhando com versionamento - cancelando últimas versões

- "Minha última versão do script não ta funcionando, quero voltar na anterior, como faço?!" - Beleza! Primeiro precisamos saber a qual commit/HEAD você precisa retornar e faze-lo.
Para ver a lista de commits/HEADs use o comando:
```
git reflog
```
A saída deve ser algo com essa carinha:

```
67d0673 (HEAD -> master, origin/master, origin/HEAD) HEAD@{0}: commit: Adiciona footer
a76b759 HEAD@{1}: Fast forward branch master to branch master
aa4a59c HEAD@{2}: commit: Ajustes gerais em CSS
7f13308 HEAD@{3}: commit: Adicionando HTML e CSS
dc206da HEAD@{4}: commit: Commit inicial
```

Digamos que você precisa voltar no commit anterior, ele seria então o equivalente ao HEAD@{1}. Para retornar, use:
```
git reset --hard HEAD@{1}
```

Para salvar esse "retorno/exclusão de commit" no repositório remoto use o comando:
```
git push origin HEAD --force
```

#### Trabalhando com branch - pare de usar arquivo(cópia 1), arquivo(cópia 2), arq....

Não use cópias, use branches! Essa frase anterior é bem bacana, por causa que ela já exemplifica o que é uma branch! Uma branch nada mais é do que uma versão paralela do código principal (que possui o nome Main ou Master default). Esse recurso é muito útil caso você queira fazer uma alteração no código mas não quer atrapalhar o código de produção com possíveis novos erros.
O exemplo clássico é o de um arquivo html pronto e funcional, você recebe a missão de adicionar um botão ao script mas não quer correr o risco de estragar o resto do código. Então cria uma branch para essa missão (nomeie a branch especificamente para essa tarefa), faça as alterações! teste muito! Tudo ok? Agora pode incluir no código principal Main/Master de produção através do comando MERGE.

Crie a branch com o comando (esse comando também serve para entrar em branchs já criadas):
```
git checkout -b nome_da_branch
```
Fez as alterações que queria? vamos salvar esse ponto do versionamento também!
```
git add nome_script
git commit -m "PALAVRA_CHAVE: descrição curta das alterações"
```
Na hora do push, vamos subir nossa branch específica ao repositório remoto com o comando:
```
git push origin nome_da_branch
```
No Github já veremos a nova branch, e podemos acessar a qualquer momento as duas versões paralelas do código. Pela plataforma você pode usar a funcionalidade MERGE, que nada mais é do que adicionar as alterações ao script principal (é um processo equivalente ao commit). Após feito o merge, exclua a branch ;)

Para ver as branchs locais, rode o comando:
```
git branch
```

Para ver as branchs remotas, rode o comando(ou olhe no github):
```
git branch -r
```

Para ver todas as branchs locais e remotas, rode o comando:
```
git branch -a
```

Para deletar branchs remotas, rode o comando:
```
git push origin --delete nome_da_branch
```

Para deletar branchs locais, rode o comando:
```
git branch -D nome_da_branch
```
#### gitignore - Ignore os arquivos desnecessários ao seu repositório....
O ".gitignore" tem a função de ignorar arquivos e pastas que vc não deseja salvar em seu repositório.
Sua sintaxe é simples! Para explicar e exemplificar ao mesmo tempo, imaginemos que temos,dentro da raiz do repositório, um arquivo "temporario.txt" e uma pasta
"temporario" com seu respectivo conteudo. Todos estes arquivos desejamos ignorar, então criamos um arquivo .gitignore e digitamos dentro dele:

```
temporario.txt
temporario/
```
Dessa forma, o arquivo txt será ignorado junto da pasta temporario e todo seu conteúdo.
ATENÇÃO: se os arquivos temporarios existiam antes da criação do .gitignore, é provável que necessitem ser excluídos, pois a regra vale a partir do momento da criação
da mesma.
</p>
