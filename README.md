log Django M3-UF6

Projecte desenvolupat amb Django dins del mòdul de Programació M3-UF6.

L'aplicació consisteix en un blog on es poden visualitzar publicacions, autors i etiquetes relacionades.

Funcionalitats
Mostrar els 3 darrers posts a la portada
Llistat complet de posts
Detall de cada post
Llistat d'autors
Perfil de cada autor amb els seus posts
Llistat de tags
Filtrat de posts per tag
Panell d'administració amb Django Admin
Pàgina 404 personalitzada
Disseny responsive amb CSS
Tecnologies utilitzades
Python
Django
HTML
CSS
SQLite
Models
Author

Representa els autors del blog.

Camps
first_name
last_name
email
Tag

Representa les etiquetes dels posts.

Camps
caption
Post

Representa les publicacions del blog.

Camps
title
excerpt
image_name
slug
content
date
author
tags
Relacions
Author ↔ Post

Relació One-To-Many:

Un autor pot tenir molts posts
Un post només pot tenir un autor
author = models.ForeignKey(Author, on_delete=models.CASCADE)
Post ↔ Tag

Relació Many-To-Many:

Un post pot tenir moltes tags
Una tag pot aparèixer en molts posts
tags = models.ManyToManyField(Tag)
Validator utilitzat

S'ha utilitzat un validator per comprovar que el contingut del post tingui una longitud mínima.

content = models.TextField(
    validators=[MinLengthValidator(10)]
)
Vistes principals
starting_page

Mostra els 3 últims posts.

posts

Mostra tots els posts ordenats per data.

post_detail

Mostra el detall d’un post segons el slug.

authors

Mostra tots els autors.

author_detail

Mostra la informació d’un autor i els seus posts.

tags

Mostra totes les etiquetes.

tag_posts

Mostra els posts relacionats amb una tag.

Templates

El projecte utilitza herència de plantilles amb:

{% extends "base.html" %}

També s’utilitzen:

{% include %}
{% static %}
{% url %}
{% for %}
Admin de Django

El projecte utilitza Django Admin per gestionar:

Posts
Authors
Tags
Fixtures

S’utilitzen fixtures per carregar dades inicials.

python manage.py loaddata blog/fixtures/initial_data.json
Executar el projecte
Instal·lar dependències
pip install django
Executar migracions
python manage.py migrate
Carregar dades inicials
python manage.py loaddata blog/fixtures/initial_data.json
Crear superusuari
python manage.py createsuperuser
Executar servidor
python manage.py runserver --insecure
GitHub

Repositori del projecte:

https://github.com/khaled22-del/Projecte_Django
Autor

Khaled Nahal Berraha

M3-UF6 — Desenvolupament Web amb Django
