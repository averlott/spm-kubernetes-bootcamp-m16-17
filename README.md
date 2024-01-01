# spm-kubernetes-bootcamp-m16-17
version kubernetes del wrapper de una aplicación web java (openjdk) para administrar contraseñas

## Entorno de Trabajo y Herramientas Utilizadas:

En primer lugar y para tener todo listo localmente clonar el repositorio.

### Vagrant ###
Con Vagrant crearemos nuestro entorno de trabajo en una maquina virtual y tambien instalaremos las herramientas necesarias para poder
desplegar nuestra aplicación (docker, docker-compose, minikube, kubectl, helm, argoCD):
1. Ejecutar el comando "vagrant up" para levantar nuestra maquina virtual.
2. Luego para poder acceder a la maquina virtual deberan ejecutar el comando "vagrant ssh".

### Docker ###
Dentro de esta carpeta encontraremos el archivo "Dockerfile" con el cual podemos crear y ejecutar la imagen de nuestra aplicación:
1. Si lo hacemos de forma manual habrá que ejecutar el comando "docker build <opciones>" y luego el comando "docker run <opciones>".
2. Si lo hacemos de forma automática ante cualquier cambio en el archivo mencionado se ejecutará un "job" de "github actions"
   que se encargará no solo de construir la imagen de nuestra aplicación sino que tambien realizará una serie de pasos para
   verificar que el código sea correcto ("linting"), detectar posibles vulnerabilidades, testear la aplicación y finalmente
   subir dicha imagen al repositorio de imagenes en "dockerhub".

### Docker-compose ###
Dentro de esta carpeta encontraremos el archivo "Dockercompose.yaml" con el cual tambien podremos crear y ejecutar la imagen de 
nuestra aplicación:
1. Si lo hacemos de forma manual habrá que ejecutar el comando "docker compose up <opciones>".
2. Si lo hacemos de forma automática ante cualquier cambio en el archivo mencionado se ejecutará un "job" de "github actions"
   que se encargará no solo de construir la imagen de nuestra aplicación sino que tambien realizará una serie de pasos para
   verificar que el código sea correcto ("linting"), detectar posibles vulnerabilidades, testear la aplicación y finalmente
   subir dicha imagen al repositorio de imagenes en "dockerhub".

### Kubernetes ###
Dentro de esta carpeta encontraremos los archivos y/o manifiestos de los recursos de "Kubernetes" definidos para desplegar
nuestra aplicacion en un cluster de Kubernetes ("minikube" en nuestro caso):
1. Si lo hacemos de forma manual habrá que ejecutar el comando "kubectl apply -f <manifiesto>" con cada uno de los recursos
   creados previamente o bien podemos ejecutar el mismo comando pero indicando un directorio en particular el cual se encuentren
   todos los manifiestos de los recursos a crear.
2. Si lo hacemos de forma automática podemos utilizar una herramienta denominada "ArgoCD" que nos facilitará realizar lo
   mencionado anteriormente.

### Helm/spm-openjdk ###
Dentro de esta carpeta encontraremos los archivos y/o manifiestos de los recursos de "Helm" definidos para desplegar
nuestra aplicacion en un cluster de Kubernetes ("minikube" en nuestro caso):
1. Si lo hacemos de forma manual habrá que ejecutar el comando "helm install <nombre_aplicacion> <directorio_helm>" con cada uno de los recursos
   creados previamente o bien podemos ejecutar el mismo comando pero indicando un directorio en particular el cual se encuentren
   todos los manifiestos de los recursos a crear.
2. Si lo hacemos de forma automática podemos utilizar una herramienta denominada "ArgoCD" que nos facilitará realizar lo
   mencionado anteriormente.
