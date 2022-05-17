# Servidor-web-Dockerizado-Nginx

Lo primero sera descargar la imagen de [DockerHub](https://hub.docker.com/_/nginx) Y ejecutaremos la imagen llamada nginx, lo que hará que la descargue y la guarde en la caché de docker 

`docker run --rm -d -p 8080:80 --name web nginx`

Ya sólo tienes que visitar http://localhost:8080 y a funcionar!

![image](https://user-images.githubusercontent.com/91567318/168858790-3fbc00c2-7d0f-4394-aa24-30f2aaf5aa05.png)

 ## Agregar HTML personalizado
lo primero que introducimos esto para detener la web
 
`docker stop web`

despues de esto nos dirijimos al escritorio y creamos una carpete

`cd /home/ciber/web`

y despues creamos un index `nano index.html` y pegamos esto 

![image](https://user-images.githubusercontent.com/91567318/168868490-313b4cae-883e-49f6-a65d-1c0687790269.png)

ahora introducimos lo siguiente y al finalizar iremos al navegador a localhost:808

docker run --rm -d -p 8080:80 --name web -v /home/ciber/web:/usr/share/nginx/html nginx

![image](https://user-images.githubusercontent.com/91567318/168869165-d016793d-27b1-4275-bc21-55b0950da191.png)

crearemos una carpeta con el nombre Dockerfile, entramos dentro y creamos un archivo 
nano Dockerfile

![image](https://user-images.githubusercontent.com/91567318/168869840-463e650e-40bc-4f64-aba3-8cae6b294c7d.png)

ahora copiaremos el archivo `index.html` en la ruta `/usr/share/nginx/html` e introducimos lo siguiente
`docker build -t webserver .`

![image](https://user-images.githubusercontent.com/91567318/168869165-d016793d-27b1-4275-bc21-55b0950da191.png)



