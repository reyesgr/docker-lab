# docker-lab
Curso Devops Laboratorio Docker
## Ejercicio 1. Creando imágenes
### Paso 1 (Sin Dockerfile)
Antes de crear directamente el contenedor miro si tengo la imagen de ubuntu descargada, no es necesario hacerlo así, pero muestro que ya la tengo por lo que se hará directamente el run y no el pull.
![](./Img/100_Img_ImagenUbuntu.png)

Creación y ejecución del contenedor creado
![](./Img/101_Img_ContenedorUbuntu.png)

Actualización del sistema
![](./Img/102_Img_ActualizacionUbuntu.png)

Instalación de curl
![](./Img/103_Img_InstalacionCurl.png)

Comprobación de funcionamiento
![](./Img/104_Img_ComprobacionCurl.png)

#### Pregunta 
#### ¿Con qué comando podrías guardar los cambios del contenedor como una nueva imagen?
docker commit <id_contenedor> <nombre_imagen>:<tag>
![](./Img/105_Img_CreacionNuevaImagen.png)
### Paso 2 (Con Dockerfile)
Creación de la imagen con Dockerfile:
![](./Img/106_Img_CreacionImagenPaso2.png)

La imagen se muestra en Docker.descktop:
![](./Img/107_Img_Imagenen%20DockerDescktopPaso2.png)

Nombrar la imagen para subirla a Docker Hub:
![](./Img/108_Img_PublicacionImagenPaso2.png)

Imagen publicada en Docker Hub:
![](./Img/109_Img_ImagenPaso2Publicada.png)

Ejecutado el contenedor basado en esa imagen y comprobado que curl está instalado:
![](./Img/110_Img_ContenedorImagenPaso2CurlInstalado.png)

#### Pregunta 
#### ¿Qué comando permite ver las capas de una imagen Docker? docker history <nombre-imagen>
![](./Img/111_Img_ContestacionPregunta2.png)

## Ejercicio 3. Volúmenes persistentes
### Paso 1 Creación, modificación e inserción de datos
Creación y ejecución de un contenedor de postgres con un volumen Docker montado en /var/lib/postgresql/data
![](./Img/111_Img_ContestacionPregunta2.png)

Creación de la tabla items en la base de datos e inserción de un dato:
![](./Img/113_Img_ContenedorPostgresCreadaTablaconDatos.png)

### Paso 2 Comprobación: parada y borrado del contenedor; nuevo contenedor
A continuación se muestra la parada y borrado del contenedor postgres-ej3
![](./Img/114_Img_ContenedorPostgresParadaBorrado.png)

Creación de un nuevo contenedor usando el mismo volumen
![](./Img/115_Img_ContenedorPostgresV1.png)

![](./Img/116_Img_ContenedorPostgresV1_b.png)

A continuación, entro en el contenedor, accedo a la base de datos y compruebo que la tabla y sus datos siguen existiendo.
![](./Img/117_Img_DatosEnNuevoContenedor.png)

## Ejercicio 4. Bind mounts
Creo un index.html, creo y ejecuto un contenedor que mapea el puerto 9000 al 80 y cuyo volumen de tipo bind monta el archivo en /usr/share/nginx/html/index.html
![](./Img/118_Img_MountBind.png)

#### Pregunta
#### ¿Qué ocurre si modificas el archivo index.html en tu máquina? 
Que se actualiza en el contenedor y el cambio también se muestra en el navegador.
![](./Img/119_Img_MountBind_Pregunta.png)

## Ejercicio 6. Creando redes privadas
Creación de la red my-net.
![](./Img/120_Img_CreacionRed.png)

Red de tipo bridge.
![](./Img/121_Img_RedTipoBridge.png)

Creación de dos contenedores en la red que acabo de crear.
![](./Img/122_Img_ContenedoresMyNet.png)

Comprobación de que están en dicha red.
![](./Img/123_Img_ContenedoresMyNet_b.png)

Realizar ping de un contenedor a otro.
![](./Img/124_Img_PingContenedores.png)

#### Pregunta
#### ¿Los contenedores pueden comunicarse entre sí?
Si, los contenedores pueden comunicarse entre sí porque están en la misma red.

## Ejercicio 9. Docker Compose --- Compartiendo volúmenes
Fichero docker-compose.yml
![](./Img/125_Img_DockerCompose.png)

Fichero Dockerfile para el Writer
![](./Img/126_Img_DockerFileWriter.png)

Fichero Dockerfile para el Reader
![](./Img/127_Img_DockerFileReader.png)

Los dos servicios en ejecución.
![](./Img/128_Img_EjecucionDockerCompose.png)
