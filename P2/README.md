## DIU - Practica2, entregables

### Ideación 
Estamos ideando **GrandTrip** para ser una plataforma que integre todas las labores que necesita un usuario al organizar un viaje en Granada. Para ello hemos realizado un exhaustivo análisis de como vamos a diseñar y elaborar nuestra aplicación.
![photo_2021-04-08_16-14-55](https://user-images.githubusercontent.com/45092820/114042302-99013e80-9885-11eb-874e-3d0b827275e7.jpg)



### PROPUESTA DE VALOR
Nuestro objetivo para diseñar esta aplicación es facilitar al usuario la organización de viajes centralizando la consulta de las tareas más habituales en un mismo software. 
La aplicación abarcará cuatro vertientes: 
- **Estancia.** Capacidad para elegir entre multitud de sitios donde hospedar; hoteles, casas rurales, alquiler de hogares. Opción de pagar tickets, entradas, reservas por la aplicación.
- **Restauración.** Obtener todos los restaurantes, bares, pubs, discotecas... de la provincia de Granada geolocalizados y valorados por usuarios que los han visitado con anterioridad. Opción de reservar entrada donde sea posible.
- **Transporte.** Información de los medios públicos de transporte del sitio de cada ciudad de la provincia así como las alternativas privadas de moda en la zona. Opción de pagar tickets, entradas, reservas por la aplicación.
- **Ocio.** Rutas deportivas por toda la provincia, excursiones recreativas. Cines, museos, casas de cultura, festivales, conciertos... Opción de reservar entrada donde sea posible.

<img width="1337" alt="Captura de pantalla 2021-04-08 a las 16 56 12" src="https://user-images.githubusercontent.com/45092820/114048995-56dafb80-988b-11eb-9571-2e706ecc291e.png">


### TASK ANALYSIS

En la siguiente tabla se identifican las tareas y su relevancia para los usuarios. Distinguimos entre cuatro grupos de usuario:
- **Estándar**: Usuario registrado en la aplicación que puede usar prácticamente todas las opciones que ofrece la aplicación salvo las reservadas para primium.
- **Premium**: Usuario registrado en la aplicación que puede usar todo lo que un estándar más entablar chat con otros usuarios premiums, escribir valoraciones y recibir notificaciones de ofertas exclusivas.
- **Promotor**: Son los usuarios/entidades que ofrece los distintos servicios de la aplicación.

🟢 **ALTO (3)
🟠 MEDIO  (2)
🔴 BAJO   (1)
❌ NO PUEDE**

| GRUPOS DE USUARIO | ESTÁNDAR | PREMIUM | PROMOTOR | NO REGISTRADOS | Ranking |
|-------------------|----------|---------|------------------|----------------|---------|
| MODO NOCHE |  🟢  | 🟢  |  🟢  | 🟢  |12 |
| CONSULTAR NOTIFICACIONES |  🟢  | 🟢 |  🟢  | 🟠  |11 |
| INICIAR SESIÓN    |  🟢  | 🟢  | 🟢  | 🔴  | 10 |
| PREGUNTAR OTROS USUARIOS |  🟢  | 🟢  | 🔴  | 🟢  |10 |
| CONSULTAR CALENDARIO |  🟢  | 🟢 |  🟢  | 🔴  |10 |
| **BUSCAR ESTANCIA**   |  🟢  | 🟢  | 🔴  | 🟠  | 10 |
| **BUSCAR RESTAURACIÓN**|  🟢  | 🟢  | 🔴  | 🟠  |10 |
| **BUSCAR TRANSPORTE**|  🟢  | 🟢  | 🔴  | 🟠  |10 |
| INFORMACIÓN DE CONTACTO   | 🟢 | 🟠  | 🟠 | 🟢|10 |
| BUSCAR OCIO |  🟢  | 🟢  | 🔴  | 🟠  |10 |
| CONSULTAR PROMOCIONES |  🟢  | 🟠  |  🟠  | 🟢  |10 |
| CHAT ONLINE |  🟠  | 🟠 |  🟢  |🟢  |10 |
| RECORDAR CONTRASEÑA   | 🟢 | 🟢 | 🟢 | ❌|9 |
| LEER FQAs   | 🟠 | 🟠 | 🟠 | 🟢|9 |
| CAMBIAR IDIOMA   | 🟢 | 🟠 | 🟢 | ❌|8 |
| HACERSE PREMIUM |  🟢  | 🔴  | 🔴  | 🟠  |7 |
| **CREAR ACTIVIDAD**  | ❌ | ❌ | 🟢 | ❌|3 |
| ALTA PROMOCIÓN   | ❌ | ❌ | 🟢 | ❌|3 |
| REGISTRARSE   | ❌ | ❌ | ❌ | 🟢|3 |
| BAJA PROMOCIÓN   | ❌ | ❌ | 🟢 | ❌|3 |
| BORRAR ACTIVIDAD | ❌ | ❌ | 🟠 | ❌|2 |
| BAJO PROMOCIÓN   | ❌ | ❌ | 🟠 | ❌|2 |


### ARQUITECTURA DE INFORMACIÓN
Proponemos la siguiente organización lógica para la navegación y para los elementos de diseño. Para ello hemos realizado un **SiteMap** en el que hemos representado las funcionalidades o servicios de la aplicación y las relaciones entre ellas. Mediante una tabla hemos representado el **labelling** del sitio, donde se inluyen los iconos que formarán parte del diseño y una breve descripción de su significado.

## SiteMap
[![](https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggVERcbkFbSG9tZV0gPT0-QihVc2VycylcbkFbSG9tZV0gPT0-QyhPZmVycylcbkFbSG9tZV0gPT0-RChBYm91dCBVcylcbkFbSG9tZV0gPT0-RShTZXR0aW5ncylcblxuXG5DIC0tPiBtKENhdGVyaW5nKVxubSAtLT4gYjIoQmFyKVxubSAtLT4gYjMoUHViKVxubSAtLT4gYjQoUmVzdGF1cmFudHMpXG5cblxuQyAtLT4gbTIoVHJhbnNwb3J0KVxubTIgLS0-IGcxKFNoYXJpbmcgY2FyKVxubTIgLS0-IGcyKEFWRSlcbm0yIC0tPiBnMyhCdXMpXG5DIC0tPiBtMyhTcGFyZSB0aW1lKVxuQyAtLT4gbTQoU3RheSlcbm00IC0tPiBnNChIb3RlbHMpXG5tNCAtLT4gZzUoU2hhcmluZyBmbGF0cylcblxubTMgLS0-IGExKEN5Y2xpbmcpXG5tMyAtLT4gYTIoUm91dGVzKVxubTMgLS0-IGEzKE11c2V1bXMpXG5tMyAtLT4gYTQoQ2luZW1hcylcbm0zIC0tPiBhNShNdXNpY2FsIGV2ZW50cylcblxuQiAtLT4gYihTaWduIHVwKVxuQiAtLT4gYyhTaWduIGluKVxuQiAtLT4gKihTaWduIG91dClcbmMgLS0-IFgoIClcbmIgLS0-IFhcblggLS0-IHooVXAgUHJlbWl1bSlcblggLS0-IGQoVXNlciBQcm9maWxlKVxuXG5EIC0tPiBoKENvbnRhY3QpXG5EIC0tPiBqKEhlbHApXG5EIC0tPiBwKEZRQXMpXG5cbkUgLS0-IGUoRGFyayBtb2RlKVxuRSAtLT4gdChMYW5ndWFnZSlcbkUgLS0-IGYoU3VwcG9ydClcbkUgLS0-IHEoSGVscClcbmogLS0-IC4oQ2hhdCBPbmxpbmUpXG5kIC0tPiAubShNeSBDYXRlcmluZylcbmQgLS0-IC55KE15IFRyYW5zcG9ydClcbmQgLS0-IC5mKE15IHNwYXJlIHRpbWUpXG5kIC0tPiAucShNeSBTdGF5cylcbi5tIC0tPiBtXG4ueSAtLT4gbTJcbi5mIC0tPiBtM1xuLnEgLS0-IG00IiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZ3JhcGggVERcbkFbSG9tZV0gPT0-QihVc2VycylcbkFbSG9tZV0gPT0-QyhPZmVycylcbkFbSG9tZV0gPT0-RChBYm91dCBVcylcbkFbSG9tZV0gPT0-RShTZXR0aW5ncylcblxuXG5DIC0tPiBtKENhdGVyaW5nKVxubSAtLT4gYjIoQmFyKVxubSAtLT4gYjMoUHViKVxubSAtLT4gYjQoUmVzdGF1cmFudHMpXG5cblxuQyAtLT4gbTIoVHJhbnNwb3J0KVxubTIgLS0-IGcxKFNoYXJpbmcgY2FyKVxubTIgLS0-IGcyKEFWRSlcbm0yIC0tPiBnMyhCdXMpXG5DIC0tPiBtMyhTcGFyZSB0aW1lKVxuQyAtLT4gbTQoU3RheSlcbm00IC0tPiBnNChIb3RlbHMpXG5tNCAtLT4gZzUoU2hhcmluZyBmbGF0cylcblxubTMgLS0-IGExKEN5Y2xpbmcpXG5tMyAtLT4gYTIoUm91dGVzKVxubTMgLS0-IGEzKE11c2V1bXMpXG5tMyAtLT4gYTQoQ2luZW1hcylcbm0zIC0tPiBhNShNdXNpY2FsIGV2ZW50cylcblxuQiAtLT4gYihTaWduIHVwKVxuQiAtLT4gYyhTaWduIGluKVxuQiAtLT4gKihTaWduIG91dClcbmMgLS0-IFgoIClcbmIgLS0-IFhcblggLS0-IHooVXAgUHJlbWl1bSlcblggLS0-IGQoVXNlciBQcm9maWxlKVxuXG5EIC0tPiBoKENvbnRhY3QpXG5EIC0tPiBqKEhlbHApXG5EIC0tPiBwKEZRQXMpXG5cbkUgLS0-IGUoRGFyayBtb2RlKVxuRSAtLT4gdChMYW5ndWFnZSlcbkUgLS0-IGYoU3VwcG9ydClcbkUgLS0-IHEoSGVscClcbmogLS0-IC4oQ2hhdCBPbmxpbmUpXG5kIC0tPiAubShNeSBDYXRlcmluZylcbmQgLS0-IC55KE15IFRyYW5zcG9ydClcbmQgLS0-IC5mKE15IHNwYXJlIHRpbWUpXG5kIC0tPiAucShNeSBTdGF5cylcbi5tIC0tPiBtXG4ueSAtLT4gbTJcbi5mIC0tPiBtM1xuLnEgLS0-IG00IiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)

## Labelling 
| TÉRMINO | ICONO | SIGNIFICADO |
|---------|-------|-------------|
|About Us | <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/aboutus.png" width="80"/>   |Zona de contacto e información sobre la organización.|
|Calendar| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/calendario.png" width="80"/> |Zona de calendario personal con los eventos y actividades por fechas.|
|Catering| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/catering.png" width="80"/>    |Zona de búsqueda de ofertas de restauración.|
|Chat Online| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/chatonline.png" width="80"/> |Chat online de ayuda.|
|Comments| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/comments.png" width="80"/> |Espacio de comentarios y valoraciones.|
|Dark mode| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/darkmode.png" width="80"/> |Activación del modo oscuro.|
|FQAs|<img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/FQAs.png" width="80"/>|Zona de preguntas frecuentes. |
|Friends| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/friends.png" width="80"/> |Zona de contactos y sugerencias de amigos.|
|Language| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/language.png" width="80"/> |Opciones de idioma de la app.|
|Logout|<img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/logout.png" width="65">| Cerrar sesión en la app.|
|Mail| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/mail.png" width="80"/> |Zona de mensajes.|
|Profile| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/usericon.png" width="80"/> |Area del perfil del usuario.|
|Settings|  <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/settings.png" width="80"/>   |Zona de ajustes.|
|Sign in|<img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/login.png" width="65"> |Iniciar sesión en la app.|
|Sign up|<img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/register.png" width="65"> | Registrarse en la app.|
|Stays| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/estancia.png" width="80"/>|Zona de búsqueda de ofertas para dormir.|
|Spare time| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/actividades.png" width="80"/> |Zona de búsqueda de actividades de entretenimiento.|
|Transport|   <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/transport.png" width="80" />|Zona de búsqueda de ofertas de movilidad.|
|Trends| <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/trends.png" width="80"/> |Actividades, sitios y diferentes sugerencias de mayor popularidad.|
|Up To Premium|<img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/uppremium.png" width="80"/>|Usuario que se suscribe al programa premium de la aplicación.|
|Users |<img src="https://github.com/pablojj1808/DIU21/blob/master/P2/img/users.png" width="80"/>|Acceder al área de usuarios.|

### Prototipo Lo-FI Wireframe 
A continuación se incluyen los bocetos Lo-Fi de las pantallas más relevantes de la interfaz.

## Sign up 
 <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/bocetosLo-Fi/SignUp.png"/>
 
## Sign in
 <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/bocetosLo-Fi/LogIn.png"/>
 
## Home
 <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/bocetosLo-Fi/Home.png"/>
 
## Options menu
 <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/bocetosLo-Fi/Opcions.png"/>
 
## Activity
 <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/bocetosLo-Fi/Element.png"/>
 
## User
 <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/bocetosLo-Fi/User.png"/>
 
## Settings
 <img src="https://github.com/pablojj1808/DIU21/blob/master/P2/bocetosLo-Fi/Settings.png"/>

### Conclusiones  
(incluye valoración de esta etapa)
