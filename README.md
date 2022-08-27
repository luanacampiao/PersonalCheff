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
- [ ] Alterar o timezone do projeto para `America/Sao_Paulo`
```
Entrar no arquivo settings e mudar TIME_ZONE = 'America/Sao_Paulo' (linha 108)
```
- [ ] Criar o app receitas

- [ ] Registrar o app receitas
- [ ] Configurar a rota inicial (index)
- [ ] Criar a view para a rota inicial
- [ ] Registrar a rota inicial
- [ ] Criar o arquivo index.html

## 📝 Licença
Esse projeto está sob licença. Veja o arquivo [LICENÇA](LICENSE.md) para mais detalhes.
[⬆ Voltar ao topo](#Personal-Cheff)<br>
