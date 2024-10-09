# Contenedores

### Crear un contenedor
Para crear un nuevo contenedor Docker a partir de una imagen específica, pero sin iniciarlo automáticamente. 

```
docker create --name <nombre contenedor> <nombre imagen>:<tag>
```
Crear el contenedor  **srv-web** usando la imagen nginx version alpine

![image](https://github.com/user-attachments/assets/7c398ac9-93f4-4588-8833-48f76d104a1f)

Si creas un contenedor en Docker sin asignarle un nombre específico utilizando la opción --name, Docker asignará automáticamente un nombre aleatorio al contenedor. Este nombre suele consistir en una combinación de palabras y números.  

Crear el contenedor usando la imagen hello-world

![image](https://github.com/user-attachments/assets/d87d0d22-a687-4151-8c74-79102fa147ab)


### Listar los contenedores ejecutándose o no

```
docker ps -a
```

### Para iniciar un contenedor

```
docker start <nombre contenedor o identificador>
```
Iniciar el contenedor srv-web 

![image](https://github.com/user-attachments/assets/6c9800cb-46e0-426e-8bda-f98f34b2fdf5)


### Listar los contenedores ejecutándose
```
docker ps 
docker ps | grep <nombre contenedor>
```

### Para detener un contenedor

```
docker stop <nombre contenedor>
```

### Para crear un contenedor y ejecutarlo inmediatamente

```
docker run --name <nombre contenedor> <nombre imagen>:<tag>
```
![Ecosistema de Docker](img/dockerRun.PNG)

Crear y ejecutar inmediatamente el contenedor **srv-web2** usando la imagen nginx:alpine

![image](https://github.com/user-attachments/assets/063da98f-ccc6-4362-8886-bfa7789dd85d)


**¿Qué sucede luego de la ejecución del comando?**

Se ejecuta inmediatamente y el terminal queda dentro de la ejecución del contenedo

Cuando ejecutas un contenedor en primer plano sin la opción -d (modo detach), el contenedor captura la entrada estándar (stdin) del terminal, lo que significa que el terminal queda "atrapado" y no puedes introducir más comandos hasta que detengas el contenedor.

### Para crear un contenedor y ejecutarlo inmediatamente sin estar vinculados al mismo
-d: Es la opción que indica a Docker que ejecute el contenedor en segundo plano (en modo "detach").
Cuando un contenedor se ejecuta en segundo plano, Docker devuelve el control al terminal inmediatamente después de iniciar el contenedor, lo que permite al usuario seguir ejecutando otros comandos en el mismo terminal sin que el contenedor detenga la interacción.

```
docker run -d --name <nombre contenedor> <nombre imagen>:tag
```
Crear y ejecutar inmediatamente el contenedor **srv-web3** en modo detach usando la imagen nginx:alpine

![image](https://github.com/user-attachments/assets/11f17b76-ead2-43f9-8b67-67be646a6b6f)


### Para eliminar un contenedor

```
docker rm <nombre contenedor>
```
Eliminar el contenedor que se creó a partir de la imagen hello-world 

![image](https://github.com/user-attachments/assets/da7c73a9-0034-4520-92da-2b8f29e359d3)

Verificar que el contenedor que se eliminó

![image](https://github.com/user-attachments/assets/5d8c4acd-6fb0-4371-af2b-79c146d74786)


### Para eliminar un contenedor que esté ejecutándose

```
docker rm -f <nombre contenedor>
```
Eliminar el contenedor **srv-web3** 

![image](https://github.com/user-attachments/assets/eb443eda-2815-497a-8a0e-2eb939cbed30)


Verificar que el contenedor que se eliminó

![image](https://github.com/user-attachments/assets/6c602b56-5f94-48cc-a976-0baaa6ae9d10)


### Para inspecionar un contenedor 

Inspeccionar el contenedor **srv-web** 

![image](https://github.com/user-attachments/assets/d17a9131-a26a-4b41-8ece-ff18237c8495)

