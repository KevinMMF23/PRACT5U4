**Proyecto de Aplicación Web con Flask: Sistema de Autenticación Simple**

## Introducción

Este proyecto demuestra la implementación básica de un sistema de autenticación web utilizando Flask, un marco web de Python. Proporciona páginas de inicio de sesión y una página de inicio con funcionalidades mínimas. El objetivo es mostrar cómo estructurar una aplicación web simple con rutas, plantillas, y formularios.

## Herramientas Utilizadas

- **Flask**: Un marco web ligero de Python para construir aplicaciones web rápidas.
- **Bootstrap**: Se utiliza para estilos y componentes de interfaz de usuario.
- **Jinja2**: Motor de plantillas para generar HTML dinámico en Flask.

## Estructura del Proyecto

- **app.py**: Punto de entrada principal para la aplicación Flask.
- **templates/**
  - **base.html**: Plantilla principal que proporciona la estructura común para todas las páginas.
  - **auth/login.html**: Página de inicio de sesión heredada de base.html.
  - **home.html**: Página de inicio que hereda de base.html.
- **static/**
  - **img/**
  - **css/**
    - **bootstrap.min.css**: Estilos de Bootstrap.
    - **login.css**: Estilos personalizados para la página de inicio de sesión.
  - **js/**
    - **bootstrap.bundle.min.js**: Biblioteca JavaScript de Bootstrap.

## Rutas de la Aplicación

- **/ (raíz)**: Redirige automáticamente a la página de inicio de sesión.
- **/login**: Página de inicio de sesión. Los usuarios pueden ingresar su nombre de usuario y contraseña.
- **/home**: Página principal después de iniciar sesión exitosamente.

## Muestra de Código

**Página de inicio de sesión (login.html):**
```html
{% extends 'base.html' %}

{% block titulo %}Login{% endblock %}

{% block miCSS %}
    <link rel="stylesheet" href="{{ url_for('static', filename='css/login.css') }}">
{% endblock %}

{% block cuerpo %}
    <h1>Login</h1>
    <form action="{{ url_for('login') }}" method="POST">
        <!-- Campos del formulario -->
    </form>
{% endblock %}
```

**Ruta de Inicio de Sesión (app.py):**
```python
@app.route("/login", methods=["GET", "POST"])
def login():
    if request.method == "POST":
        # Procesar datos del formulario
        if _user == "admin" and _pass == "123":
            return redirect(url_for("home"))
        else:
            return render_template("auth/login.html")
    else:
        return render_template("auth/login.html")
```

## Marco Teórico

- **Flask**: Flask es un marco web ligero de Python que sigue el principio de "hazlo simple". Proporciona las herramientas necesarias para construir aplicaciones web rápidas y eficientes sin imponer decisiones o bibliotecas preexistentes.

- **Herencia de Plantillas (Jinja2)**: La herencia de plantillas permite crear una plantilla base con un diseño común y extenderla en plantillas específicas para reutilizar el diseño común. Esto ayuda a evitar la duplicación de código HTML y CSS.

## Conclusiones

Este proyecto sirve como punto de partida para comprender y construir aplicaciones web con Flask. Proporciona una estructura básica que puede expandirse con funcionalidades adicionales, como registro de usuarios, almacenamiento de contraseñas seguras, etc.

Espero que esta aplicación web sirva como introducción útil a Flask y proporcione una base sólida para futuros desarrollos.

---

Siéntete libre de personalizar este README según tus necesidades y preferencias antes de agregarlo a tu repositorio en GitHub. ¡Espero que te sea útil!
