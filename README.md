# CLASE-IWEB-9-Jakarta


## JSP / HTML Diferencias

JSP es como un código en HTML que emplea JAVA. No le mandamos JSP sino pasamos de JSP  a HTML y luego se manda al usuario.

## Servidor APACHE TOMCAT
Es para realizar servicios no complejos

## SERVLET
Es una clase especial de Java que es punto intermedio entre la página JSP y el servidor Web. Los servlet se encargan de recibir PETICIONES y REQUEST de un cliente. Servlet nos servirá para unir las clases de JAVA con las peticiones del cliente.

## Creación de un proyecto en Jakarta

1) Crear el proyecto
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/2ae5259b-88af-46ad-8e76-d6f122bdd247)
   
2) Clic en Jakarta. Asignamos la ubicación en donde se guardará el proyecto, el Tomcat y le damos a Web Application.
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/d2e19ca7-d610-4727-bb14-c44f03a044c2)

3) Elegimos la versión del Jakarta y la dependencia del Servlet:
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/0709678e-2226-4dcd-b47e-e83faefbfbcb)

## Análisis del entorno de Jakarta

Vemos que se crea un archivo pom.xml donde van las dependencias que necesitaremos en el proyecto.

Tenemos el archivo index.jsp en la que hay una mezcla entre código HTML y Java.

Para tener código Java en mi página web necesita tener extensión "jsp".

En la carpeta "resources" se púede colocar imágenes, videos, javascripts.

![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/926e0845-4a76-4998-87df-d2a3eeee78b9)

## Servlets
Son una clase especial para poder comunicar peticiones Web mediante protocolo HTTP.

Cada Servlet tiene un propio nombre que se empleará en su ruta para que Tomcat lo encuentre. La importancia radica en que si yo en el buscador de url pongo la ruta para buscarla con la ruta del Servlet Tomcat sí podrá ubicar la clase.

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/a217edfc-f90c-4bff-89c8-39d0aca68951)

Ejemplo Stuardo de url (web) cómo llega a la clase en Java:

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/99cdb9d5-1010-4229-aba0-f02b250751a4)

NOTA: no colocar espacios en el nomnbre de los Servlets porque genera problemas en la compilación.

## Creación Servlets forma Antigua

1) Primero copiamos y pegamos el servlet creado por default en otra clase
2) Luego cambiamos el nombre del "name", "value" y de la clase public class.

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/4f29ca4c-89df-469c-b7a2-5020919f471d)

## Problemas Compilación Servlets Tomcat

El formato de un url de un Servlet es: [protocolo] / [socket(ip + puerto)] / [Proyecto] / [ruta] . De no seguir este formato, podrían haber problemas en la compilación.

1)

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/24b2402c-2599-40fb-ac31-dc1e46ac9649)

2) Revisamos el url en el que se compila nuestro proyecto

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/7bbc884a-47e7-424a-80c3-49bd281f7684)

   
3) En Deployment, podemos ver la versión del Tomcat y el nombre del proyecto (podemos cambiarlo)
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/519ade10-8cbb-4650-9b24-a1a834fabd01)

## Compilación del proyecto en Jakarta

Vemos que no hemos asignado una ruta en el url, por lo que el servidor de Tomcat, por default, buscará un archivo llamado index de cualquier clase de extensión (.py, .js, etc). En nuestro caso tenemos un archivo llamado "index.jsp" por lo que compiló ese archivo.

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/1e17bbf8-0041-4785-a28f-823be93e51fe)

## Protocolo HTTP

protocolo que tiene métodos POST, GET, DELETE, PUT y HEAD. En IWEB solo veremos GET y POST.

Todos los FORMULARIOS son POST por lo general.

La búsqueda por url es GET, igualmente los botones que emplean href usan GET.

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/c56fe4ac-05e3-42d4-a4ff-098769f340ab)

Es por ello que la interfaz de los Servlets se hará en el método GET para las url. Cuando tengamos formularios serán para el método POST en el respectivo Servlet.

REQUEST: Es lo enviado por el usuario (Ingreso de url). En base a ello, podemos extraer información de la propia url

RESPONSE: Respuesta que será enviada mediante el server Tomcat (Lo que se mande por RESPONSE será la respuesta)

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/b83463fd-c8f9-4777-ac86-e5f70b713c7c)

Ejemplo del RESPONSE:

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/7ba9ba81-15f2-4eb1-bdb1-f67601f884fa)

## Creación de Servlet que liste todos los trabajos (EJERCICIO)

1) Creamos la clase Job (modelado de la tabla como clase) y colocamos los Getters y Setters a sus atributos private
   
2) En el JobServlet, declaramos el driver, parámetros de conexión, conexión a DB (hr) y extraemos con un while(rs.next()) cada fila hasta que este vacía, extraemos el id, nombre, etc.Luego lo añadimos al ArrayList de tipo de dato Job para guardar cada job.
   
3) Luego con un for each en el arrayList listaJob, obtenemos el nombre. Entonces obtendremos un listado de nombres de los puestos de trabajo:
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/4c0f660d-44ec-46cc-8b22-a926efed7305)

El problema ahora es si queremos una interfaz más amigable, tendríamos que codear HTML, pero en 1 solo string (no agradable), por lo que para ello se empleará MVC.

## -------------------- MVC --------------------











