# FlaskFirstProject



## PASOS

PASO 1) Seguir los pasos (1-10) para creacion de ambiente (test19) y activacion del mismo disponibles en README.md de https://github.com/lmarcela/DjangoFirstApp

PASO 2) Activar el ambiente, instalar Flask, ejecutar archivo :

		E:\PYTHON\DJANGO\ambientes\test19\Scripts>activate
		(test19) E:\PYTHON\DJANGO\ambientes\test19\Scripts>pip install Flask

		(test19) E:\PYTHON\DJANGO\ambientes\test19>cd E:\PYTHON\FLASK\Tutorial Udemy\flask_introduction

		(test19) E:\PYTHON\FLASK\Tutorial Udemy\flask_introduction>python run_app.py

		NOTA: Se descargo proyecto de base de https://github.com/rmotr/flask-introduction

PASO 3) Seguir explicacion del curso de Udemy: https://www.udemy.com/python-flask-tutorial-step-by-step/learn/v4/overview

PASO 4) Para la parte de bases de datos correr por consola el comando: 
		
		//Esto creara una bd sqlite con el esquema definido en el archivo library-schema.sql
		sqlite3 library.db < library-schema.sql

PASO 5) Para insertar datos en la base de datos correr por consola el comando:

		//Esto insertara datos en la bd con las instrucciones definidas en el archivo initial-data.sql
		sqlite3 library.db < initial-data.sql
		
PASO 6) import g: permite declarar variables globales. @app.before_request: permite definir algo que siempre se va a ejecutar antes de cualquier proceso (puede ser util para verificar si un usuario se encuentra logueado).

		//Esto se ejecutara siempre antes de hacer un proceso en las rutas
		@app.before_request
		def before_request():
			g.db = connect_db()
			
		//Y puede ser usado por otros de forma global
		@app.route('/')
		def hello_world():
			cursor = g.db.execute('SELECT id, name FROM author;')
			authors = [dict(id=row[0], name=row[1]) for row in cursor.fetchall()]
			return render_template('database/authors_template_engine.html', authors=authors)

PASO 7) @app.route('/', methods=['POST', 'GET']). Metodos de acceso a la ruta. Por defecto es GET.

PASO 8) href="{{ url_for('static', filename='bootstrap.css') }}". Referencia a css.
		
## Comandos Flask:

- Empezar app: python run_app.py

## GIT COMMANDS:
		git init
		git add .
		git commit -m "first commit"
		git git remote add origin https://github.com/lmarcela/FlaskFirstProject.git
		git push -u origin master

