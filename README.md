# Personal Cheff
<!---Esses são exemplos. Veja https://shields.io para outras pessoas ou para personalizar este conjunto de escudos. Você pode querer incluir dependências, status do projeto e informações de licença aqui--->
![Python](https://img.shields.io/badge/Python-14354C?style=for-the-badge&logo=python&logoColor=white)
![Django](https://img.shields.io/badge/Django-092E20?style=for-the-badge&logo=django&logoColor=white)
![HTML](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
<img src="Receitas-Capa-1.png" alt="exemplo imagem">
> Uma aplicação web de receitas chamada PersonalCheff desenvolvida durante o curso de Python no Senac Americana. A aplicação listará receitas e clicando em cada nome de receita você pode ver a receita completa.
### Lista de tarefas
Segue a lista de tarefas a serem desenvolvidas no projeto:
- [X] Pré-requisitos
    - [X] Instalar o Python
    - [X] Instalar Visual Studio Code

- [X] Criar e ativar o ambiente virtual
``` 
Para criar o ambiente virtual: abrir terminal, prompt de comando de digitar: 
python -m venv .\venv\       
(se der erro, é necessário checar versão, no terminal: pynthon--version, se for python 2,  checar se há o python3 instalado: python3--version. 
Se for o 3 instalado necessário digitar python3 no código acima)
Para ativar o ambiente virtual, digitar: 
venv\Scripts\activate
```
- [x] Instalar o Django
```
Entrar no site do Django e veja qual versão terá suporte por mais tempo. Em seguida, no terminal:
python -m pip install django==3.2
```
- [x] Criar o Projeto PersonalCheff
```
Digitar no terminal:
django-admin help (ou django-admin.py help) pra ver a lista de comandos.
Para criar o projeto: 
django-admin startproject PersonalCheffProj
```
- [x] Subir o servidor e testar o projeto
```
Abrir a pasta do projeto no terminal:
cd nomedapasta
Subir o servidor (testar o projeto): 
python manage.py runserver
Clicar no link do servidor para abrir a página.
```

- [x] Alterar o idioma do projeto para `pt-br`
```
Entrar no arquivo settings.py do projeto e trocar idioma para LANGUAGE_CODE = 'pt-br' (linha 106). Enquanto servidor estiver rodando atualiza automaticamente, se parar necessário rodar o runserver novamente.
```
- [x] Alterar o timezone do projeto para `America/Sao_Paulo`
```
Entrar no arquivo settings e mudar TIME_ZONE = 'America/Sao_Paulo' (linha 108)
```
- [x] Criar o app receitas
```
Abre outro terminal (clica novamente em prompt comando e renomeia, deixa o servidor rodando em um prompt e o outro será para uso)
Uma aplicação pode estar em mais de um projeto.
Para criar uma aplicação, entra na pasta do projeto:
cd PersonalCheffProj
Depois cria a aplicação:
python manage.py startapp receitas
```
- [x] Registrar o app receitas
```
Entrar no arquivo apps da pasta receitas, e checar o nome da aplicação.
Entra no arquivo settings do PersonalChefProj e encontrar INSTALLED_APPS, aplicações que já possuem (linha 33) e adicionar a aplicação 'receitas'(nome igual está na pasta apps)
```
- [x] Configurar a rota inicial (index)
```
- Criar um arquivo chamado: urls.py
- Escrever dentro dele:
from django.urls import path
from . import views

urlpatterns = [
    path('',views.index, name='index')
]
```
- [x] Criar a view para a rota inicial
```
- Dentro do arquivo views na pasta receitas:
from django.shortcuts import render
from django.http import HttpResponse

def index(request):
    return HttpResponse("Seja Bem Vindo")
```

- [x] Registrar a rota inicial
```
- Dentro da pasta url do projeto, a partir da linha 16:

from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('receitas.urls')),
]
```


- [x] Criar o arquivo index.html

- Dentro da pasta receitas(app) criar a pasta templates
- Dentro da pasta templates criar os arquivos html, começando pelo index.html
- Dentro do arquivo index: !(enter), muda lingua, adiciona o titulo 1  e titulo2 
- No arquivo views do app (receitas) faça a seguinte alteração do código, apaga tudo e colocar:

```
from django.shortcuts import render

def index(request):
    return render(request,'index.html')
```
 - [X] Integrar arquivos estáticos (CSS, JS, IMG)
    - Dentro da pasta do projeto (PersonalCheffProj) criar uma pasta chamada 'static'
    - Dentro da pasta 'static', colocar as imagens, os arquivos css e os arquivos js que for utilizar
    - no arquivo 'settings.py':
        - Realize a importação da biblioteca 'os' através do comando 'import os', ainda no 'settings.py', na linha 58 'DIRS' adicione o caminho dos templates da seguinte forma:
        ```python
        'DIRS': [os.path.join(BASE_DIR,'receitas/templates')],
        ```
 - [ ] Utilizando links
 - [ ] Criando o base.html
 - [ ] Separando em partials
 - [ ] Renderizando dados dinamicamente
 - [ ] Criando um dicionario com as receitas
 - [ ] Criando o banco de dados(MySQL/MariaDB)
 - [ ] Instalando o conector do bando de dados MySQL
 - [ ] Criando o modelo da receita
 - [ ] Criando a migration (mapeamento)
 - [ ] Realizando a migration
 - [ ] Registrando um modelo no admin
 - [ ] Criando um usuário para o ambiente administrativo


## 📝 Licença
Esse projeto está sob licença. Veja o arquivo [LICENÇA](LICENSE.md) para mais detalhes.
[⬆ Voltar ao topo](#Personal-Cheff)<br>
