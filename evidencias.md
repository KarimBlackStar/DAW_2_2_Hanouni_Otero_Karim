# EVIDENCIAS

Creo el contenedor

![img.png](img.png)

el contenedor temporal intenta conectarse a cache por su nombre, 
pero falla porque la red por defecto de 
Docker (bridge) no proporciona resolución DNS entre contenedores

![img_1.png](img_1.png)

El comando ping se utiliza para verificar la conectividad de red y el estado de salud del servicio. 
Al recibir la respuesta PONG, tenemos la confirmación empírica de que el contenedor responde 
y que la comunicación directa a través de la IP en la red bridge funciona correctamente, 
compensando la falta de resolución DNS.

![img_2.png](img_2.png)

Creo la red personalizada y conecto el contenedor

![img_5.png](img_5.png)

El valor se encuentra almacenado en la memoria RAM asignada al contenedor cache2 
y en su capa efímera de lectura y escritura.

![img_3.png](img_3.png)

**Explica por qué en la configuración de una aplicación se usan nombres de contenedor y no
direcciones IP, y por qué para todo esto no ha hecho falta publicar ningún puerto.**


En las configuraciones de aplicaciones se utilizan los nombres de los contenedores 
porque sus direcciones IP son dinámicas y cambian cada vez que se reinician o se vuelven a crear, 
mientras que el nombre permanece estático. No es necesario publicar puertos (usando -p) \
porque todos los contenedores que comparten la misma red interna de Docker 
tienen acceso a todos sus puertos recíprocamente de forma predeterminada.

Al destruir los contenedores sin haber configurado previamente volúmenes persistentes, 
todos los datos almacenados en ellos se pierden de forma permanente.

![img_4.png](img_4.png)