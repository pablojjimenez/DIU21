## DIU - Practica2, entregables

### Ideación 
Estamos ideando **GrandTrip** para ser una plataforma que intgre todas las labores que necesita un usuario al organizar un viaje en Granada. Para ello hemos realizado un exhaustivo análisis de como vamos a diseñar y elaborar nuestra aplicación.
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
## SiteMap
[![](https://mermaid.ink/img/eyJjb2RlIjoiZ3JhcGggVERcbkFbSG9tZV0gPT0-QihVc2VycylcbkFbSG9tZV0gPT0-QyhPZmVycylcbkFbSG9tZV0gPT0-RChBYm91dCBVcylcbkFbSG9tZV0gPT0-RShTZXR0aW5ncylcblxuXG5DIC0tPiBtKENhdGVyaW5nKVxubSAtLT4gYjIoQmFyKVxubSAtLT4gYjMoUHViKVxubSAtLT4gYjQoUmVzdGF1cmFudHMpXG5cblxuQyAtLT4gbTIoVHJhbnNwb3J0KVxubTIgLS0-IGcxKFNoYXJpbmcgY2FyKVxubTIgLS0-IGcyKEFWRSlcbm0yIC0tPiBnMyhCdXMpXG5DIC0tPiBtMyhTcGFyZSB0aW1lKVxuQyAtLT4gbTQoU3RheSlcbm00IC0tPiBnNChIb3RlbHMpXG5tNCAtLT4gZzUoU2hhcmluZyBmbGF0cylcblxubTMgLS0-IGExKEN5Y2xpbmcpXG5tMyAtLT4gYTIoUm91dGVzKVxubTMgLS0-IGEzKE11c2V1bXMpXG5tMyAtLT4gYTQoQ2luZW1hcylcbm0zIC0tPiBhNShNdXNpY2FsIGV2ZW50cylcblxuQiAtLT4gYihTaWduIHVwKVxuQiAtLT4gYyhTaWduIGluKVxuQiAtLT4gKihTaWduIG91dClcbmMgLS0-IFgoIClcbmIgLS0-IFhcblggLS0-IHooVXAgUHJlbWl1bSlcblggLS0-IGQoVXNlciBQcm9maWxlKVxuXG5EIC0tPiBoKENvbnRhY3QpXG5EIC0tPiBqKEhlbHApXG5EIC0tPiBwKEZRQXMpXG5cbkUgLS0-IGUoRGFyayBtb2RlKVxuRSAtLT4gdChMYW5ndWFnZSlcbkUgLS0-IGYoU3VwcG9ydClcbkUgLS0-IHEoSGVscClcbmogLS0-IC4oQ2hhdCBPbmxpbmUpXG5kIC0tPiAubShNeSBDYXRlcmluZylcbmQgLS0-IC55KE15IFRyYW5zcG9ydClcbmQgLS0-IC5mKE15IHNwYXJlIHRpbWUpXG5kIC0tPiAucShNeSBTdGF5cylcbi5tIC0tPiBtXG4ueSAtLT4gbTJcbi5mIC0tPiBtM1xuLnEgLS0-IG00IiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)](https://mermaid-js.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZ3JhcGggVERcbkFbSG9tZV0gPT0-QihVc2VycylcbkFbSG9tZV0gPT0-QyhPZmVycylcbkFbSG9tZV0gPT0-RChBYm91dCBVcylcbkFbSG9tZV0gPT0-RShTZXR0aW5ncylcblxuXG5DIC0tPiBtKENhdGVyaW5nKVxubSAtLT4gYjIoQmFyKVxubSAtLT4gYjMoUHViKVxubSAtLT4gYjQoUmVzdGF1cmFudHMpXG5cblxuQyAtLT4gbTIoVHJhbnNwb3J0KVxubTIgLS0-IGcxKFNoYXJpbmcgY2FyKVxubTIgLS0-IGcyKEFWRSlcbm0yIC0tPiBnMyhCdXMpXG5DIC0tPiBtMyhTcGFyZSB0aW1lKVxuQyAtLT4gbTQoU3RheSlcbm00IC0tPiBnNChIb3RlbHMpXG5tNCAtLT4gZzUoU2hhcmluZyBmbGF0cylcblxubTMgLS0-IGExKEN5Y2xpbmcpXG5tMyAtLT4gYTIoUm91dGVzKVxubTMgLS0-IGEzKE11c2V1bXMpXG5tMyAtLT4gYTQoQ2luZW1hcylcbm0zIC0tPiBhNShNdXNpY2FsIGV2ZW50cylcblxuQiAtLT4gYihTaWduIHVwKVxuQiAtLT4gYyhTaWduIGluKVxuQiAtLT4gKihTaWduIG91dClcbmMgLS0-IFgoIClcbmIgLS0-IFhcblggLS0-IHooVXAgUHJlbWl1bSlcblggLS0-IGQoVXNlciBQcm9maWxlKVxuXG5EIC0tPiBoKENvbnRhY3QpXG5EIC0tPiBqKEhlbHApXG5EIC0tPiBwKEZRQXMpXG5cbkUgLS0-IGUoRGFyayBtb2RlKVxuRSAtLT4gdChMYW5ndWFnZSlcbkUgLS0-IGYoU3VwcG9ydClcbkUgLS0-IHEoSGVscClcbmogLS0-IC4oQ2hhdCBPbmxpbmUpXG5kIC0tPiAubShNeSBDYXRlcmluZylcbmQgLS0-IC55KE15IFRyYW5zcG9ydClcbmQgLS0-IC5mKE15IHNwYXJlIHRpbWUpXG5kIC0tPiAucShNeSBTdGF5cylcbi5tIC0tPiBtXG4ueSAtLT4gbTJcbi5mIC0tPiBtM1xuLnEgLS0-IG00IiwibWVybWFpZCI6eyJ0aGVtZSI6ImRlZmF1bHQifSwidXBkYXRlRWRpdG9yIjpmYWxzZX0)

## Labelling 
| TÉRMINO | ICONO | SIGNIFICADO |
|---------|-------|-------------|
|FQAs|![icono exclamacion](https://github.com/pablojj1808/DIU21/blob/master/P2/img/FQAs.png = 250x250) |Zona de preguntas frecuentes. |
|About Us |  ![istockphoto-1184299108-1024x1024](https://user-images.githubusercontent.com/45092820/114897530-9d8f9f00-9e11-11eb-933c-3b56ea61616b.jpg)  |Zona de contacto e información sobre la organización.|
|Settings|   ![settings-cogwheel-button_icon-icons com_72559](https://user-images.githubusercontent.com/45092820/114897721-cadc4d00-9e11-11eb-9a33-26746435892f.png)
    |Zona de ajustes.|
|Chat Online|   ![network_society_communication_online_chat_icon_143342](https://user-images.githubusercontent.com/45092820/114897758-d760a580-9e11-11eb-8136-be9c1ba82906.png)
    |Chat online de ayuda.|
|Catering| ![-local-dining_90278](https://user-images.githubusercontent.com/45092820/114897826-e6dfee80-9e11-11eb-976b-f267eed1ad63.png)
|Zona de búsqueda de ofertas de restauración.|
|Transport|       |Zona de búsqueda de ofertas de movilidad.|
|Spare time|       |Zona de búsqueda de actividades de entretenimiento.||
|Stays|       |Zona de búsqueda de ofertas para dormir.||
|Users |       |Acceder al área de usuarios.|
|Up Premium|       |Usuario que se suscribe al programa premium de la aplicación.|
|Sign up|       | Registrarse en la app.            |
|Sign in|       |Iniciar sesión en la app.|
|Sign out|      | Cerrar sesión en la app.|

>> https://icon-icons.com/es/buscar/iconos/?filtro=transport
### Prototipo Lo-FI Wireframe 


### Conclusiones  
(incluye valoración de esta etapa)
