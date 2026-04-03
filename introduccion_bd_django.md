# Introducción a bases de datos en Django

## 1. Bases de datos en Django

### ¿Qué función cumple una base de datos dentro de una aplicación Django?
Una base de datos permite almacenar, organizar y recuperar la información que utiliza una aplicación Django. Por ejemplo, sirve para guardar usuarios, productos, libros, pedidos o cualquier otro dato necesario para el funcionamiento del sistema. Django se conecta a la base de datos para leer, insertar, actualizar y eliminar información.

### ¿Qué sistemas de bases de datos relacionales soporta Django por defecto?
Django soporta por defecto los siguientes sistemas de bases de datos relacionales:

- SQLite
- PostgreSQL
- MySQL
- Oracle

### ¿Cuál es el motor de base de datos que se utiliza por defecto al crear un nuevo proyecto? ¿Por qué crees que es ese?
El motor de base de datos que Django utiliza por defecto es **SQLite**.

Creo que es el motor por defecto porque es muy fácil de usar, no necesita instalación adicional ni configuración compleja, y permite comenzar a desarrollar rápidamente. Es ideal para proyectos pequeños, pruebas y aprendizaje.

---

## 2. ORM en Django

### ¿Qué es un ORM y cómo se diferencia de escribir sentencias SQL manualmente?
ORM significa **Object-Relational Mapping**. Es una herramienta que permite trabajar con la base de datos usando clases y objetos de Python en vez de escribir sentencias SQL manualmente.

La diferencia principal es que, con SQL manual, el programador debe escribir consultas como `SELECT`, `INSERT`, `UPDATE` o `DELETE` directamente. En cambio, con el ORM de Django, esas operaciones se realizan usando métodos de Python, lo que hace el código más simple y legible.

### Menciona al menos dos ventajas de usar el ORM de Django
Dos ventajas de usar el ORM de Django son:

- Permite trabajar con la base de datos usando Python, sin necesidad de escribir SQL en la mayoría de los casos.
- Hace el código más claro, ordenado y fácil de mantener.
- Ayuda a que la aplicación sea más portable entre distintos motores de base de datos.
- Reduce errores al manejar consultas complejas de forma más segura.

### Explica qué significa que una clase modelo en Python represente una tabla en la base de datos
Significa que cada clase definida en `models.py` corresponde a una tabla en la base de datos. Además, cada atributo de esa clase representa una columna de la tabla.

Por ejemplo, si existe una clase `Libro`, Django crea una tabla asociada para almacenar los datos de los libros. Si la clase tiene campos como `titulo`, `autor` y `publicado`, entonces la tabla tendrá columnas con esos mismos datos.

---

## 3. Migraciones

### ¿Qué son las migraciones en Django y por qué son importantes?
Las migraciones en Django son archivos que registran los cambios realizados en los modelos de la aplicación. Sirven para que esos cambios se apliquen de forma ordenada en la estructura de la base de datos.

Son importantes porque permiten crear o modificar tablas, columnas y relaciones sin tener que hacerlo manualmente en SQL. También ayudan a mantener sincronizados los modelos de Python con la base de datos.

### ¿Qué comandos se utilizan para crear y aplicar migraciones?

#### Crear una nueva migración a partir de cambios en los modelos
```bash
python manage.py makemigrations
python manage.py migrate
