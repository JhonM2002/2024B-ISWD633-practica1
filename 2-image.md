# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](img/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
Una imagen es un archivo que contiene todo lo necesario para ejecutar una aplicación, como el código y sus dependencias, mientras que un contenedor es una instancia activa de esa imagen, en la que la aplicación se ejecuta en un entorno aislado. La imagen es inmutable y actúa como una plantilla, mientras que el contenedor es mutable y opera en tiempo de ejecución, lo que permite flexibilidad y escalabilidad al ejecutar múltiples contenedores basados en la misma imagen.

![Imagen y contenedores](img/imagenContenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**
![image](https://github.com/user-attachments/assets/8f356e32-aa80-4b09-8238-0cb32be5dfbb)

**¿Qué es nginx**
Nginx es un servidor web de código abierto que también puede funcionar como servidor proxy inverso, balanceador de carga, y caché HTTP.

Descargar la imagen  **nginx** en la versión **alpine**
![image](https://github.com/user-attachments/assets/984433e2-ef22-4eb3-8850-7fa280cd1945)

### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 
![image](https://github.com/user-attachments/assets/90a5140b-cfdb-4cb5-a6eb-1449068b73f3)

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
![image](https://github.com/user-attachments/assets/3462d1a2-bd41-4c93-8685-5d5ecbd8ba5b)

**¿Con qué algoritmo se está generando el ID de la imagen**
Con el algoritmo de hash SHA-256
### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
![image](https://github.com/user-attachments/assets/7e9cd68e-b199-48d9-ae04-db3f9ac99261)

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

