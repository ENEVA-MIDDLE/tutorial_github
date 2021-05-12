<h1 align="center">Manual de utilização do github</h1> 
<h4 align="center">🚀Tutorial de como usar o github de forma prática🚀</h4>

<p> 
O GIT é um software de versionamento de códigos, voltado a facilitar a gestão das versões e atualizações em scripts.
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



</p>
