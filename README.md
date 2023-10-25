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

La búsqueda por url es GET, igualmente los botones que emplean href usan GET. Sirve para solicitar al servidor un recurso y obtenerlos (HTML, JPG, PDF,etc)

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/c56fe4ac-05e3-42d4-a4ff-098769f340ab)

Es por ello que la interfaz de los Servlets se hará en el método GET para las url. Cuando tengamos formularios serán para el método POST (doPost) en el respectivo Servlet.

REQUEST: Es lo enviado por el usuario (Ingreso de url). En base a ello, podemos extraer información de la propia url

RESPONSE: Respuesta que será enviada mediante el server Tomcat (Lo que se mande por RESPONSE será la respuesta)

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/b83463fd-c8f9-4777-ac86-e5f70b713c7c)

Ejemplo del RESPONSE:

  ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/7ba9ba81-15f2-4eb1-bdb1-f67601f884fa)

## URL Estructura
De toda la url lo que esté después del ? serán parámetros y están separados por & 

Ejemplo: ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/27c31790-2264-46fc-b298-a14c6beaf335)

## Creación de Servlet que liste todos los trabajos (EJERCICIO)

1) Creamos la clase Job (modelado de la tabla como clase) y colocamos los Getters y Setters a sus atributos private
   
2) En el JobServlet, declaramos el driver, parámetros de conexión, conexión a DB (hr) y extraemos con un while(rs.next()) cada fila hasta que este vacía, extraemos el id, nombre, etc.Luego lo añadimos al ArrayList de tipo de dato Job para guardar cada job.
   
3) Luego con un for each en el arrayList listaJob, obtenemos el nombre. Entonces obtendremos un listado de nombres de los puestos de trabajo:
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/4c0f660d-44ec-46cc-8b22-a926efed7305)

El problema ahora es si queremos una interfaz más amigable, tendríamos que codear HTML, pero en 1 solo string (no agradable), por lo que para ello se empleará MVC.

## -------------------- MVC --------------------

MVC (Model-View-Controller) es un patrón de diseño que separa la aplicación en 3 capas para una mejor organización.

Las 3 capas son:

1) Modelo: Representa todo lo relacionado a acceso de datos (para nuestro proyecto sería todo lo relacionado a Base de Datos). (DAOS, BEANS y DTO) 
2) Vista: Contiene la parte visual de la pag web. (JSP)
3) Controlador: Contiene la lógica de la aplicación. (SERVLET)

## Creación de paquetes (Package)

1)
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/e2e2d1ad-eed1-46f1-bac8-10fcabfcfe5f)

2) Luego escogemos el nombre del package (carpeta): Daos, Beans, Servlets y View. View ya está por default como WebApp

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/b5cace45-d0e8-4508-82a3-a88d5e47c93a)

3) Colocamos cada clase creada (Daos, Beans, Jsp, Servlets) en su respectiva capa (package)
   
## Justificación del uso de los Beans

Tenemos el JobDao (procesamiento en base a Base de Datos):

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/d0dc57fc-ff56-448f-8325-60b13ca2fcae)

Sin embargo, vemos que el JobServlet necesita de una lista 

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/fdf0deb5-19ec-434e-9e15-c887f8da058b)

Es por ello, que el envío de datos (retornar valores) del DAO hacia el SERVLET (de su respectiva tabla) será el BEAN.

## Beans
Sirven para poder enviar o retornar algo del Dao hacia el Servlet.

El Bean es una representación de una tabla de Base de Datos. Es por ello que como atributos debería tener todas las columnas que tiene una tabla en la Base de Datos.

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/932ce8ba-c78b-411c-92e7-151d971043cd)

Por eso Job es un Bean.

## Método que retorna Arraylist

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/43c9141c-0afb-45f2-8e9b-51cb002ee786)

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/7a23d60b-fd77-4663-b83a-95b6e309ead3)

## FUNCIONAMIENTO BEAN-SERVLET-DAO

1) Bean es Job 

2) 

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/7bbce121-3d4f-4373-83ed-163e3e0ee98b)

3) 

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/f87cdba7-4811-4e6d-a8f0-5d7485e524ae)

Vemos que hay parte de View en JobServlet, por eso creamos archivo jsp.

## Creación JSP
1) Se creará una carpeta por cada tabla o espacio de trabajo DENTRO DE WEBAPP

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/4800866b-7c00-436a-a02f-9402cf341688)

2) Crear el archivo jsp dentro de la carpeta creada

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/bbec3741-4cbd-46d6-811d-db85f748b6f5)

## FUNCIONAMIENTO SERVLET (Mandar "algo" a la vista)

1) Extraemos del modelo (Dao) la información: Lista
   
2) Con request.setAtributte seleccionamos qué vamos a mandar a la vista ("mensaje",cosa_para_mandar)

3) Mandamos la lista a la vista mediante la clase RequestDispatcher que sale del request, con ello mandamos la información a la vista.
   
4) Darle el paso a View con el método forward del "rd" mandando el request y response. Asimismo tenemos que colocar el ServletExcepetion porque el forward es un checkedException.
   
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/8d14291e-0c3a-4344-b828-ec44e637f8e2)

## Recepción de "algo" de la vista mandada por el Servlet

1) Importar el Bean (lo puede hacer solo la maquina, autocorección).
2) Crear el ArrayList, pero tenemos que castear lo enviado. Además, lo enviado lo catalogamos con el mensaje que pusimos a la hora de enviar.
   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/7dbcf419-d213-4eb9-99f4-e3d589d076a3)

   Con el Request.getAtributte("mensaje") nosostros recepcionamos algo enviado por el Servlet, en este caso casteamos a Arraylist.

## Impresión en HTML

Para poder imprimir desde Java a HTML debemos poner entre los scritles el signo igual "<%= %>". 

No es recomendable escribir comentarios al costado de los <td> y los <tr> porque también se mezclan con el código.

< tr > : sirve para trabajar en una fila
   
< td > : sirve para trabajar en columna

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/0ff62224-b21a-436f-bfc6-9128335381ed)

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/5bf54521-ef7b-44b6-ab47-60dd73ba4d8a)


Explicación funcionalidades sacadas de Bootstrap:

en class = "table table-stripted mt-3". 

table-stripted y mt-3 son parámetros que cambian la tabla. Se colocaran los parámetros de esa forma (hacia la derecha) sin quitar la primera palabra "table".

"table-stripted" pinta una fila sí y la siguiente no, suesivamente.

"mt-3" significa margin-top 3

Con "table-primary" es asignarle un color a una fila. Se sobreescribe este color sobre el ya dispueto por el "table-stripted"

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/7ebba1cd-1323-4be1-8c2c-236ac0d13372)

Resultado final:

   ![image](https://github.com/SergioABS0813/CLASE-IWEB-9/assets/134556600/6a850d6e-4d60-44e5-8d30-435a50732b89)

Ahora, podemos ver full código HTML debido a que el jsp (combinación entre Java y HTML) cuando pasa por el servidor Tomcat, lo convierte en full HTML y luego esto es enviado al usuario para que vea dicha interfaz web.

## Servlet a la mano (Crear Servlets sin necesidad de emplear método arcaico)

Diapositivas Stuardo clase 9.2 IWEB



