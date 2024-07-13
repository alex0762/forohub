# API Foro Hub

_ Un espacio donde todos los participantes de una plataforma pueden plantear sus preguntas y respuestas sobre determinados tópicos. este es mi proyecto, llamado ForoHub: en él, vamos a replicar este proceso a nivel de back end y, para eso, crearemos una API REST usando Spring.

Nuestra API se centrará específicamente en los tópicos y sus respuestas, y debe permitir a los usuarios:

Crear un nuevo tópico/ respuesta ;
Mostrar todos los tópicos/ respuestas creados;
Mostrar un tópico/ respuesta específico;
Actualizar un tópico/ respuesta;
Eliminar un tópico/ respuesta.
 CRUD* (CREATE, READ, UPDATE, DELETE)._

## Comenzando 🚀

_Estas instrucciones te permitirán obtener una copia del proyecto en funcionamiento en tu máquina local para propósitos de desarrollo y pruebas._

Mira **Deployment** para conocer como desplegar el proyecto.


### Pre-requisitos 📋

_IntelliJ IDEa, Insomnia (para pruebas) , PgAdmin4 son las herramientas a utilizar_

```
https://www.jetbrains.com/es-es/idea/download/?section=windows
```
```
https://www.jetbrains.com/es-es/idea/download/?section=windows
```
```
https://www.postgresql.org/download/
```

### Instalación 🔧

_Antes de iniciar el servicio deberá crear una nueva base de datos con el nombre: foro_hub_

_Clone este repositorio_

```
https://github.com/SamuelVelascoH/ForoHub-API-REST.git
```

_Abra el proyecto desde IntelliJ IDEA (Open new file) con la ruta de su repositorio local, verifique los siguientes datos en el archivo .propierties: spring.datasource.username=${SU_USUARIO_DE_SU_DB}, pring.datasource.password=${LA_CONTRASEÑA_DE_SU_DB}, así como la ruta de su base de datos spring.datasource.url=jdbc:postgresql://localhost:SU_RUTA/foro_hub y api.security.secret=${JWT_SECRET:(12345 por defecto)}, despues de esto debera iniciar el servicio.
las URI para las pruebas son las siguientes_

_Para crear un usuario de tipo UserForo (debera usar el metodo HTTP: POST, el cuerpo de tipo JSON y la URI) a continuacion:_
```
 http://localhost:8080/user
```
 ```
{
    "email" : "tu email" ,
	"userName" : "tu usuario" ,
	"password" : "tu contraseña"
}
```
_Para actualizar un usuario de tipo UserForo (debera usar el metodo HTTP: PUT, el cuerpo de tipo JSON y la URI) a continuacion:_
```
http://localhost:8080/user/{id}
```
```
{ "id" : "id del usuario" ,
	"email" : "tu nuevo email" ,
	"userName" : "tu nuevo usduario" ,
	"password" : "tu nueva contraseña"
}
```
_Para listar todos los usuarios de tipo UserForo (debera usar el metodo HTTP: GET y la URI) a continuacion::_
```
http://localhost:8080/user
```
_Para obtener un usuario de tipo UserForo por su ID (debera usar el metodo HTTP: GET la URI(el "id" apunta a el user a actualizar)) a continuacion:_
```
http://localhost:8080/user/{id}
```
_Para eliminar un usuario de tipo UserForo (debera usar el metodo HTTP: DELETE, el cuerpo de tipo JSON y la URI (el "id" apunta a el user a actualizar)) a continuacion:_
```
http://localhost:8080/user/{5}
```
_Para crear un Topico (debera usar el metodo HTTP: POST, el cuerpo de tipo JSON y la URI) a continuacion:_
```
http://localhost:8080/topics
```
```
{
	"title" : "tu titulo" ,
	"body" : "tu tema" ,
	"courseName" : "tu nombre de curso"
}
```
_Para actualizar un Topico (debera usar el metodo HTTP: PUT, el cuerpo de tipo JSON y la URI) a continuacion:_
```
http://localhost:8080/topics/{id}
```
```
{ "id" : "id del topico" , 
	"title" : "tu nuevo titulo" ,
	"body" : "tu nuevo tema" ,
	"courseName" : "nombre del curso"
}
```
_Para listar todos Topicos (debera usar el metodo HTTP: GET, el cuerpo de tipo JSON y la URI) a continuacion:_
```
http://localhost:8080/topics
```
_Para obtener un Topico por su ID (debera usar el metodo HTTP: GET, el cuerpo de tipo JSON y la URI) a continuacion:_
```
http://localhost:8080/topics/{id}
```
_Para eliminar un Topico (debera usar el metodo HTTP: DELETE, el cuerpo de tipo JSON y la URI) a continuacion:_
```
http://localhost:8080/topics/{id}
```
_Para crear una repuesta (debera usar el metodo HTTP: POST, el cuerpo de tipo JSON y la URI) a continuacion, (el "id" apunta hacia el topico al que va dirigida la respuesta)_
```
http://localhost:8080/response/{id}
```
```
{"id" : "id del topico",
    "responseTitle": "el titulo de tu respuesta",
    "body": "tu respuesta"
}
```
_Para actualizar una repuesta (debera usar el metodo HTTP: PUT, el cuerpo de tipo JSON y la URI) a continuacion (el "id" apunta hacia la respuesta a actualizar)_
```
http://localhost:8080/response/{id}
```
```
{"id" : "id de la respuesta",
    "responseTitle": "el titulo de tu nueva respuesta",
    "body": "tu nueva respuesta"
}
```
_Para listar todas las repuestas (debera usar el metodo HTTP: GET, el cuerpo de tipo JSON y la URI) a continuacion_
```
http://localhost:8080/response
```
_Para obtener una repuesta por su ID (debera usar el metodo HTTP: GET, el cuerpo de tipo JSON y la URI) a continuacion_
```
http://localhost:8080/response/{id}
```
_Para eliminar una respuesta (debera usar el metodo HTTP: DELETE, el cuerpo de tipo JSON y la URI) a continuacion_
```
http://localhost:8080/response/{id}
```

_Finaliza con un ejemplo de cómo obtener datos del sistema o como usarlos para una pequeña demo_

## Ejecutando las pruebas ⚙️

_La API usa un token de seguridad para cada usuario (JWT) por lo que deberá autenticarse para poder ejecutar pruebas, el usuario y contraseña deberan estar previamente registrados en su base de datos con la contraseña ya cifrada, para el hashing de la contraseña se esta usando el algoritmo Bcrypt _

### Para autenticar un usuario🔩

_La URI para la autenticación es la siguiente_

```
http://localhost:8080/login
```
_JSON para la autenticación_

```
{
	"login" : "tu usuario" ,
	"key" : "tu contraseña"
}
```
_Generador de hash Bcrypt_

```
https://bcrypt.online/
```


### Ahora puede ejecutar las pruebas⌨️

_Para un uso completo de la Api autentiquese como usuario de tipo UserApi, esto le permitira crear actualizar y eliminar usuarion de tipo UserForo, recuerde que su usuario y contraseña deben estar previamente guardadas en su base de datos, en este caso, si prefiere, en la tabla users_api_

## Gracias! 
