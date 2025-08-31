1. Diferencia HTTP vs HTTPS y rol TLS

HTTP es un protocolo de comunicación entre cliente y servidor, pero no cifra la información.
HTTPS usa TLS para cifrar la comunicación y proteger datos sensibles, como contraseñas o formularios.

2. WSGI y ASGI en Python (Django)

WSGI es la interfaz estándar para apps web síncronas en Python.
ASGI es su evolución, soporta apps asíncronas (WebSockets, streaming).
Django soporta ambos, pero por defecto usa WSGI.

3. Registro A y CNAME en DNS

Un registro A apunta un dominio a una dirección IP.
Un registro CNAME apunta un dominio a otro dominio.
Ej: api.miapp.com → 34.231.90.12 (A) vs www.miapp.com → miapp.com (CNAME).

4. REST: GET vs POST (ejemplo del sistema)

GET se usa para leer datos → /proyectos/ lista proyectos.
POST se usa para crear datos → formulario para crear nueva tarea.

5. Capa MVC que controla el flujo en Django

En Django, las Views actúan como Controlador, gestionan las peticiones y preparan los datos para las Templates.

Parte 5 — Flujo de petición/respuesta HTTP

Al visitar /proyectos/ se realiza un GET y Django responde 200 OK, mostrando la lista de proyectos activos. Al abrir /proyectos/<id>/ se envía otro GET con 200 OK, mostrando los detalles del proyecto y sus tareas asociadas. Al enviar el formulario de nueva tarea en /proyectos/<id>/tareas/nueva/ se hace un POST, Django crea la tarea en la base de datos y responde 302 Found, redirigiendo al detalle del proyecto, donde un GET devuelve 200 OK y muestra la vista actualizada. El recurso creado es un nuevo registro en la tabla Tarea, el cual se refleja inmediatamente en la lista de tareas del proyecto.
