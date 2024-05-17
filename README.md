# Grafana-y-Prometheus

Queremos en nuestra maquina virtual de Azure gracias a Docker utilizar Grafana y Prometheus además de Nginx para ver nuestra página. Para eso haremos estos pasos:
1.	Acceso a la Máquina Virtual
2.	Instalar Nginx
3.	Instalar Docker para ejecutar Prometheus y Grafana.


Paso 1: Instalar y configurar Nginx
1.	Instalamos Nginx:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/6f6631af-289a-4cfd-97c6-f27b9bd669c7)
2.	Configura la redirección en Nginx:
   
![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/fc570e40-9341-4ee4-a528-fdd0a3118632)

4.	Reiniciamos Nginx
5.	Ejecutamos el exporter 
![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/3be6a6e8-1d4a-485a-a044-bc990a2478ff)


Paso 2: Instalar Docker
1.	Instala Docker:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/f10d61bf-7d80-4b7c-b6b5-33cf5950d3b6)

2.	Añadimos el usuario a Docker:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/fe957af8-41bb-4a93-b2a8-f6770c948202)

Comprobamos que funciona con un Docker run hello-world:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/e60110ec-a2c6-413a-b3a7-a73775be1363)

Ponemos los puertos 9090 y 3000 para acceder a prometheus y grafana:
![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/a86e99b0-075b-4d6c-8f1d-e1ec32177b7e)
![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/2814bdeb-b27d-45c7-ac6d-89d2f5af81b0)



Paso 3: Configurar Prometheus y Grafana
1.	Crea un archivo de configuración para Prometheus:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/71b3b6a7-91c4-42e4-aa6c-df9d7c9479c0)

2.	Ejecuta Prometheus en un contenedor Docker
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/83793248-a6cd-41f5-a2d1-e360dacb1ec6)

3.	Ejecutamos Grafana
![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/dfa64d47-06a5-41c4-8681-0486be0c505e)

Paso 4: Configurar Grafana , Prometehus y Exporter
1.	Vemos que tenemos parados las imágenes de prometheus, grafana y exporter así que la ejecutamos:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/8d8d955c-8ea9-4c46-8260-773ad6e779ce)

2.	Los ejecutamos y pasan de Exited a UP
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/e2b80837-d0bf-420a-ae32-14420e29ccf5)

3.	Entramos en el navegador poniendo la ip/3000 para entrar a Grafana:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/9d2918cd-b9f7-466a-a011-8b8f93014d01)

4.	Conectamos Prometheus como fuente de datos en Grafana poniendo como url la ip/9090 que es donde esta prometheus:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/08343b69-dd1a-4e39-911b-6ac408956861)

5.	Creamos un dashboard con los datos de prometheus, en este caso es la cpu que utiliza en los últimos 5 minutos.
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/718dd9bd-254a-488f-9a65-831c3d315c36)

6.	Abrimos prometehus y hacemos algunas pruebas up(vemos que pone 1 que es que esta funcionando), go_info que nos da diferente info, y por ultimo tenemos un grafico de la cpu utilizada.
 
![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/de672ff1-8d6a-4aef-9e45-c27127bbe656)



7.	Abrimos la ip nuestra y vemos nuestra pagina de github gracias al Nginx
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/22018fc4-6e10-4c46-b8b2-9856e1a33e54)


