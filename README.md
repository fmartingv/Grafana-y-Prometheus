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
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/88b9ca67-7e8d-4bf1-b145-ea623bb2795a)


2.	Ejecuta Prometheus en un contenedor Docker
![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/860bc0c5-8e82-4d82-815f-eeb0e8057d0d)


3.	Ejecutamos Grafana
![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/39801a32-1fb5-4647-a0b3-145c66cd9551)


Paso 4: Configurar Grafana , Prometehus y Exporter
1.	Vemos que tenemos parados las imágenes de prometheus, grafana y exporter así que la ejecutamos:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/b69189a5-9719-455d-bd42-f17688d30d87)


2.	Los ejecutamos y pasan de Exited a UP
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/6e897b4b-8dab-4336-99f4-3baad1aab70f)


3.	Entramos en el navegador poniendo la ip/3000 para entrar a Grafana:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/5c25a561-7cc4-48b8-830b-f268e3149d78)


4.	Conectamos Prometheus como fuente de datos en Grafana poniendo como url la ip/9090 que es donde esta prometheus:
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/08343b69-dd1a-4e39-911b-6ac408956861)

5.	Creamos un dashboard con los datos de prometheus, en este caso es la cpu que utiliza en los últimos 5 minutos.
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/718dd9bd-254a-488f-9a65-831c3d315c36)

6.	Abrimos prometehus y hacemos algunas pruebas up(vemos que pone 1 que es que esta funcionando), go_info que nos da diferente info, y por ultimo tenemos un grafico de la cpu utilizada.
 
![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/de672ff1-8d6a-4aef-9e45-c27127bbe656)



7.	Abrimos la ip nuestra y vemos nuestra pagina de github gracias al Nginx
 ![image](https://github.com/fmartingv/Grafana-y-Prometheus/assets/120713266/22018fc4-6e10-4c46-b8b2-9856e1a33e54)


