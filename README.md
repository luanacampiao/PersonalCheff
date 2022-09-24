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
        - linha  'DIRS': Realize a importação da biblioteca 'os' através do comando 'import os', ainda no 'settings.py', adicione o caminho dos templates da seguinte forma:
        ```python
        'DIRS': [os.path.join(BASE_DIR,'receitas/templates')],
        ```
        - linha 122 abaixo de 'STATIC_URL', adicione a seguinte linha:
        ```python
        STATIC_ROOT = Ele cria/envia arquivos para a pasta 'static' principal. É a configuração da rota através do comando; os.path.join(BASE_DIR,'static')
        STATICFILES_DIR = [
            os.path.join(BASE_DIR,'PersonalCheffProj/static')
        ]
        ```
        Para testar, ir até o terminal e executar o comando: 'python manage.py collectstatic' , uma pasta chamada 'static' deverá ser criada na pasta raíz.<br>
    - Inserir {% load static %} na primeira linha do arquivo index.html (dentro da pasta template). Este comando deve ser usado em todos os arquivos que você for utilizar arquivos estáticos.
    - Insira uma imagem utilizando o comando <img src="{% static 'cheff_imagem.png' %}"> . Sempre que for utilizar um arquivo estático você deve utilizar <img src="{% static 'nomedoarquivodeimagemcomextensão'}">  
    - Criar um arquivo chamado estilos.css dentro da pasta 'static' do projeto para inserir informações de formatação da página:
    ```css
    body{
    background-color: #cacaca;
    color: #181818;
    font-family: 'Segoe UI';

}

.cheff_imagem{
    width: 150px;
}

.tabela-receitas{
    width: 90%;
}

.sucodelaranja_imagem{
    width: 80px;
}
```
    - no arquivo index.html adicionar os links:
```python
         Para conectar a página html ao arquivo estilos.css:
        <link rel="stylesheet" href="{% static 'estilos.css' %}">
        Para inserir a imagem na aba da página:
        <link rel="shortcut icon" href="{% static 'cheff_imagem.png'%}"
        type="image/x-icon">
    
```

 - [X] Utilizando links
    - Para criar um link para a página index, independente de onde você esteja utilize o comando 'url':
    ```python
    <a href="{% url 'index' %}">Página Inicial</a>
    ```

 - [X] Criando o base.html
    - na pasta templatescrie o arquivo base.html. Esse arquivo contém todo o código de estrutura comum à todas as páginas. Nesse arquivo deve ficar tudo que tiver antes do body e tudo que tiver depois do /body.
    - nesse arquivo deve conter o {% load static %}
    - nesse arquivo, no local aonde será carregado o conteúdo das outras páginas, deve existir os delimitadores {% block content %} e {% endblock %}
    - o código do base.html será algo parecido com:
    ```python
    {% load static %}
    <!DOCTYPE html>
    <html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>PersonalCheff</title>
        <link rel="stylesheet" href="{% static 'estilos.css' %}">
        <link rel="shortcut icon" href="{% static 'logo.png' %}" type="image/x-icon">
    </head>
    <body>
    {% block content %}
 
    
    {% endblock %}
    </body>
    </html>
    ```

 - [X] Separando em partials
    - criar uma pasta chamada partials dentro da pasta templates
    - dentro da pasta partials crie os arquivos que serão as partes globais utilizadas no seu projeto como header.html, footer.html, menu.html, side-bar.html, banner.html, etc. No nosso exemplo criamos as partials header.html e footer.html
    - insira em cada um dos arquivos partials seus códigos correspondentes. Exemplo: no arquivo header.html eu insiro todo o conteúdo que eu quero que seja apresentado no cabeçalho da minha aplicação. Não se esqueça do comando {% load static %}.
    - para incluir as partials nos arquivos de destino utilize o comando include da seguinte maneira: {% include 'partials/header.html' %}
 - [X] Renderizando dados dinamicamente
    É trocar as informações fixas do arquivo html por informações dinâmicas vindas do arquivo python
    - Quero gerar a lista de receiras de forma dinâmica, vamos fazer isso utilizando o recurso do Django que passa uma informação para minhas templates(.html) através da passagem de um parâmetro no comando 'render' que está em minha view(.py):
    ```python
    return render(request,'index.html',
    {'nome_da_receita':'suco de laranja'})
    ```
    - Observe que passei através do comando 'render' um 'dicionário' para a template. Na minha template ('index.htlm') eu posso exibir o conteúdo desse dicionário da seguinte forma:
    ```python
    <td><img src="{% static 'sucodelaranja_imagem.png' %}" class="icone-suco">
    {{nome_da_receita}}</td>
    ```
    - Vale a pena diferenciar o uso de '{{}} e '{% %}:
        - `{{}}` é utilizado normalmente para exivir o valor de variáveis, para mostrar informarções na tela.
        -  `{% %}` é utilizado para o processamento de informações, usamos esses delimitadores quando precisamos de `if`ou `for` por exemplo.
 - [X] Criando um dicionario com as receitas
    - No arquivo `views.py` vamos criar um dicionário com as receitas, modifique a função `index` da seguinte forma:
    ```python
    def index(request):
    receitas={
        1:'Suco de Melão',
        2:'Pizza',
        3:'Macarrão',
        4:'Panquecas'
    }
    
    dados = {
        'lista_receitas': receitas
    }
    return render(request,'index.html',dados)
    ```
    - na template `index.html`, fazer um laço de repetição que verifique cada item da lista de receitas à cada passagem do laço:
    ```pyhton
    {% for chave, uma_receita in lista_receitas.items %}
            <tr>
                <td>
                    <img src="{% static 'sucodelaranja_imagem.png' %}" 
                    class="icone-suco">
                    {{uma_receita}}
                </td>
                <td>https://www.youtube.com/watch?v=Nn9140bDPnc</td>
                <td>
                    <a href="{% url 'sucodelaranja' %}" class= "btn btn-dark">Ver receita completa</a></td>
            </tr>
        {% endfor%}
    ```
 - [X] Criando o banco de dados(MySQL/MariaDB)
    - Abrir o XAMPP e start os serviços dp Apache e MySQL
    - Click no botão admin do Apache
    - Acesse o link PHPMyAdmin
    - Dentro do PHPMyAdmin, click no botão `novo` para criar um banco de dados, insira o nome `personalcheff_bd`
     
 - [ ] Instalando o conector do bando de dados MySQL
 - [ ] Criando o modelo da receita
 - [ ] Criando a migration (mapeamento)
 - [ ] Realizando a migration
 - [ ] Registrando um modelo no admin
 - [ ] Criando um usuário para o ambiente administrativo
 

## 📝 Licença
Esse projeto está sob licença. Veja o arquivo [LICENÇA](LICENSE.md) para mais detalhes.
[⬆ Voltar ao topo](#Personal-Cheff)<br>
