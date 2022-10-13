# Apod-LWC
A través de la interacción con este componente web en Salesforce, podrás conocer sobre hechos astronómicos obtenidos por la API Astronomy Picture of the day publicada por la NASA. Además de obtener una redacción de audio otorgado por el servicio de IBM Cloud Text-to-speech. 
Requisitos:
- Organización Salesforce
- VSCode y Salesforce extensión pack.
- CLI Salesforce
- Generar apikey de https://api.nasa.gov/
- Generar cuenta de https://cloud.ibm.com/
- Crear Servicio text-to-speech https://www.ibm.com/mx-es/cloud/watson-text-to-speech?utm_content=SRCWW&p1=Search&p4=43700052790840473&p5=e&gclid=Cj0KCQjwyOuYBhCGARIsAIdGQRMLJfoXt_SGaYn39QQ6LxFMo2UEDTu-cUVVwJ1jFU62HBuBbZCmN6waAvzTEALw_wcB&gclsrc=aw.ds

Procedimiento de instalación LWC
1.- Generamos un nuevo Proyecto y autorizamos nuestra organización con ayuda de la paleta de comandos de visual studio code, Ctrl + Shift + P.
![image](https://user-images.githubusercontent.com/86945047/195680384-44a8066d-7903-4102-8be9-ce1359c5e061.png)

2.- Ya que hemos autorizado nuestra organización procedemos a pegar el archivo apodPackage.zip en nuestro directorio raíz del proyecto.
![image](https://user-images.githubusercontent.com/86945047/195680635-cbba9ef3-f0c6-4092-a6eb-ba2b63c655c4.png)

3.- Abrimos una terminal dentro de nuestro proyecto en visual studio code y procedemos a ejecutar el siguiente comando sfdx force:mdapi:deploy -f apodPackage.zip

![image](https://user-images.githubusercontent.com/86945047/195680708-10e56332-c193-4068-a499-5b6f0a3b048a.png)

4.- Ejecutamos el siguiente comando sugerido por la terminal para revisar el estado de nuestro deploy.
![image](https://user-images.githubusercontent.com/86945047/195680763-18c269a4-d8c1-4cff-a827-73551f07d2c8.png)

5.-Notaremos que nuestro deploy ha sido exitoso.
![image](https://user-images.githubusercontent.com/86945047/195680846-02e30f0e-249d-4e4e-be04-070566463775.png)

6.- Cuando nuestro deploy este listo procedemos a configurar nuestra organización. Para ello nos dirigimos a Setup, escribimos Themes y seleccionamos la opción Themes and Branding.

![image](https://user-images.githubusercontent.com/86945047/195680919-0de1cbb0-58e0-48a5-be01-d93cf796748b.png)

7. Buscamos el Tema ApodApp y lo activamos.

![image](https://user-images.githubusercontent.com/86945047/195681001-ff3916dd-f61f-4117-9454-ae3dc631153c.png)

8.- Una vez activado procedemos a configurar nuestra clase apex para ello dentro de Setup nos dirigimos a la sección Apex Classes y seleccionamos editar en la clase ApodController.

![image](https://user-images.githubusercontent.com/86945047/195681064-b0ed3045-4e89-4df1-8343-6ccb3c72818f.png)

9.- Ahora configuraremos nuestro web service APOD para ello procedemos a editar el valor de la variable apikey en la línea 10, con nuestra respectiva key generada en la página https://api.nasa.gov/ 

![image](https://user-images.githubusercontent.com/86945047/195681331-f524cbae-4bd9-4d75-8b81-84b2e2df49eb.png)

10. Ahora configuraremos nuestro web service de Text to speech del servicio de IBM Cloud, una vez generado nuestro servicio, procedemos a editar el valor de nuestra variable endpointCloudService en la línea 32 con la URL de la instancia creada. De igual manera editamos el valor de la variable apikeyCloudService con nuestra key correspondiente.

![image](https://user-images.githubusercontent.com/86945047/195681384-852a98a1-ed6f-48b7-a033-8ec73197979f.png)

11.- Una vez realizados estos cambios procedemos a guardar nuestra clase.

![image](https://user-images.githubusercontent.com/86945047/195681436-60ec9af6-e1c1-4404-b154-a320b642b5b2.png)

12.- Ahora procederemos a activar nuestra Tab personalizada. Para ello seleccionamos la opción Profiles dentro de Setup y seleccionamos el perfil correspondiente, en este caso System administrator.

![image](https://user-images.githubusercontent.com/86945047/195681522-fe946b3d-6c7b-49ce-8c10-75b0a3bc40fd.png)

![image](https://user-images.githubusercontent.com/86945047/195681549-93d6d976-e00c-4c1d-8222-5ff27a3d0c67.png)

13.- Presionamos editar perfil y nos desplazamos hacia abajo hasta la sección Custom Tab Settings, y modificamos el valor a Default On.

![image](https://user-images.githubusercontent.com/86945047/195681622-6d2573f0-38f4-4042-b771-3d6a7924c547.png)

14.- Una vez guardados estos cambios en el perfil, podremos acceder a nuestro componente desde el apartado de App Launcher buscando Apod API App.

![image](https://user-images.githubusercontent.com/86945047/195681697-e6403a1b-86fc-46f6-bbfa-0eff0bd005b0.png)

15. Ahora nuestro componente está listo para usar.

![image](https://user-images.githubusercontent.com/86945047/195681771-74595ba7-a20d-4fa0-97b8-8c265c50f2df.png)

![image](https://user-images.githubusercontent.com/86945047/195681794-f158a658-b89e-4a0c-8f90-a430be1d5c82.png)



