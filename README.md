# Práctica 4.4 (semana del 23 al 27 Enero): deployment of an architecture EFS-EC2-MultiAZ in the CLoud (AWS)


## Pasos a seguir:

1. Nos vamos a la ec2 y le damos a grupos de seguridad para posteriormente crear el grupo web con el puerto 80 y el sgweb con el puerto 2049

![img](img/1.png)

![img](img/2.png)

![img](img/3.png)

    1.1 En el grupo de seguridad SGWeb añadiremos la siguiente regla de entrada

![img](img/4.png)

2. Ahora lanzaremos una instancia

![img](img/instancia1.png)

![img](img/instancia1-1.png)

![img](img/instancia1-2.png)

![img](img/instancia1-3.png)

3. lanzaremos otra identica aunque le cambiaremos lo siguiente

![img](img/instancia2.png)

![img](img/instancia2-1.png)

4. Ahora montaremos el servicio nfs

![img](img/nfs1.png)

    4.1 Accedemos al nfs y le damos a el apartado de red y le damos a administrar.
    Y en la zona 1a y 1b elegimos el siguiente grupo de seguridad, ya que son las únicas que vamos a usar.

![img](img/nfs2.png)

![img](img/nfs3.png)

Copiaremos el id en el notepad para usarlo mas tarde y no tener que ir buscandolo.

5. Nos conectamos a las máquinas ec2.

![img](img/conectarnosec2.png)

6. Nos vamos a la carpeta var/www/html con el siguiente comando y creamos la siguiente carpeta con este comando.

![img](img/comandosec2.png)

7. Podremos el siguiente comando, pero tendremos que cambiar el id que nos viene por el id de nuestro nfs que guardamos antes.

![img](img/comandosec2-2.png)

8. Ahora meteremos nuestros archivos de la página web mediante una url. Tabien descomprimiremos la carpeta netflix.zip con el siguiente comando

![img](img/comandosec2-3.png)

![img](img/comandosec2-4.png)

9. Hacemos exactamente lo mismo en la otra máquina ec2, lo único que no haremos es descomprimir la carpeta netflix.zip

10. Ahora modificaremos el fichero httpd.conf para en el buscador nos salga la pagina de netflix solamente poniendo la ip

![img](img/editar-httpdconf.png)

11. Ahora cambiaremos el documentRoot para que redirija a la carpeta efs-mount. Y reiniciamos el apache:

![img](img/editar-httpdconf-2.png)

![img](img/reiniciarapache.png)
