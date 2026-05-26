# Blog Django M3-UF6

Projecte desenvolupat amb Django dins del mòdul de Programació M3-UF6.

L'aplicació consisteix en un blog on es poden visualitzar publicacions, autors i etiquetes relacionades.

---

# Funcionalitats

- Mostrar els 3 darrers posts a la portada
- Llistat complet de posts
- Detall de cada post
- Llistat d'autors
- Perfil de cada autor amb els seus posts
- Llistat de tags
- Filtrat de posts per tag
- Panell d'administració amb Django Admin
- Pàgina 404 personalitzada
- Disseny responsive amb CSS

---

# Tecnologies utilitzades

- Python
- Django
- HTML
- CSS
- SQLite

---

# Models

## Author

Representa els autors del blog.

### Camps

- first_name
- last_name
- email

---

## Tag

Representa les etiquetes dels posts.

### Camps

- caption

---

## Post

Representa les publicacions del blog.

### Camps

- title
- excerpt
- image_name
- slug
- content
- date
- author
- tags

---

# Relacions

## Author ↔ Post

Relació One-To-Many:

- Un autor pot tenir molts posts
- Un post només pot tenir un autor

```python
author = models.ForeignKey(
    Author,
    on_delete=models.CASCADE
)
