# Python on Replit

This is a template to get you started with Python on Replit. It's ready to go so you can just hit run and start coding!

## Running the repl

1. Setup a new secret environment variable (the lock icon) where the key is `SECRET_KEY` and the value is
   a randomly generated token of 32 bits of randomnese. To generate such a token type this into the shell and hit Enter:
```
python
import secrets
secrets.token_urlsafe(32)
```
2. Hit run!

See this 1 minute video for a walkthrough: [https://www.loom.com/share/ecc4e738149f4d1db3bcff01758b3e71](https://www.loom.com/share/341b5574d12040fb9fcbbff150777f1c)

## Installing packages

To add packages to your repl, you can just import directly in the file you want to use the package in, and it will automatically be installed when you press the run button. Like below:
```python
import math
import pandas as pd
```

You could also install packages by using the Replit packager interface in the left sidebar.

## Help

If you need help you might be able to find an answer on our [docs](https://docs.replit.com) page. Feel free to report bugs and give us feedback [here](https://replit.com/support).

### Nome do projeto 

Project name: django2

### Banco de Dados utilizado 

Database used: db.sqlite3

### Comandos

django-admin startproject django2 .
pip install django
pip freeze > requirements.txt

Para criar uma aplicação: django-admin startapp core

linux: ls 
windows: dir
linux: pwd # imprime o nome do diretório de trabalho
django-admin startapp core
python manage.py runserver
ctrl + c para parar o servidor

### Configurações de settings

settings > INSTALLED_APPS = [  'core', ] # ctrl + s para salvar a aplicação criada

settings > TEMPLATES > 'DIRS': ['templates'], # eu estou informando para a configuração do projeto que os o diretório e o diretório de templates será um diretório chamado templates que irei criar depois dentro da aplicação.

Templates páginas HTML e CSS  

### Comando para executar o sistema

python manage.py runserver

### Migrações 

Migrations that were performed on the system:

python manage.py makemigrations
python manage.py migrate

### informações sobre o comando

python manage.py help makemigrations 
python manage.py help migrate
python manage.py help runserver
python manage.py help createsuperuser
python manage.py collectstatic

### Super usuário
python manage.py createsuperuser

### Usando o shell

python manage.py shell
>>> from core.models import Produto
>>> dir(Produto) # acesso aos atributos
>>> from core.views import index
>>> dir(index)
>>> produto = Produto("Atari 2600", 199.67, 100)
>>> dir(produto)
>>> produto.save()
>>> 
### Quando não tem construtor

>>> produto = Produto(nome="Atari 2600", preco=199.67, estoque=100)
>>> produto.save()
>>> dir(produto)
>>> produto.id
>>> produto.pk

>>> from core.models import Cliente
>>> cliente = Cliente(nome='Angelina', sobrenome'Jolie', email='angelina@gmail.com')
>>> cliente.save()
>>> cliente.pk
>>> cliente.id
>>> cliente
>>> print(cliente)
>>> cliente.nome = 'Maria'
>>> cliente.save()
>>> cliente.pk
>>> cliente.id
>>> cliente.delete()

### Request

core > views.py

print(request)

print(dir(request))
print(f'Metodo: {request.method}')
print(f'Headers: {request.headers}')
print(f"Headers: {request.headers['User.Agent']}")
print(f"User.Agent: {request.headers['User.Agent']}") # qual o navegador, o sistema operacional, versão do navegador que o usuário está utilizando
print(f"User: {request.user}")
print(dir(request.user))
print(f"User: {request.user.last_name}")
print(f"User: {request.user.email}")

if str(request.user) == 'AnonymousUser':
    teste = 'Usuário não logado'
else:
    teste = 'Usuário logado'
    context = {
        'curso': 'Programação Web com Django Framework',
        'outro': 'Django é massa!',
        'logado': teste

core > index.html
<body>
	<span>{{ logado }}</span>
</body>

### Apresentação de dados do banco de dados no template

python manage.py shell
>>> from core.models import Produto
>>> dir(Produto)
>>> dir(Produto.objects)
>>> produtos = Produto.objects.all()
>>> produtos
>>> for produto in produtos:
...   print(produto)
>>> Produto.objects.count()
>>> Produto.objects.first()
>>> Produto.objects.last()
>>> Produto.objects.filter(id=1)

python manage.py shell
>>> from core.models import Produto
>>> prod = Produto.objects.get(1)
>>> type = Produto.objects.get(1)
>>> dir(Produto.objects.get(1))
>>> Produto.objects.get(1).first()
>>> Produto.objects.filter(id=1).first()
>>> help(Produto.objects.get)
>>> prod = Produto.objects.get(id=1)
>>> prod

python manage.py shell
>>> from core.models import Produto
>>> dir(Produto)
>>> dir(Produto.objects.get.(id=1))
>>>
### Arquivos estáticos

python manage.py shell

>>> from django_project.settings import BASE_DIR
>>> BASE_DIR

### Visite o projeto no Replit

https://django2.deisefreire2022.repl.co/

