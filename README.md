# Semana 1
Servidor de correo

instalación del docker:

paso 1
- sudo apt-get update
- dependencias:
  - sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common
<p><img src="https://user-images.githubusercontent.com/71399485/109642832-c145a100-7b53-11eb-9207-a21785d1e82f.png" alt="Cat"></p>
paso2
  - Descargue la clave GPG oficial de Docker para verificar la integridad de los paquetes antes de instalar:
    - curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
  - Agregue el repositorio de Docker al repositorio de su sistema con el siguiente comando:
    - sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/debian buster stable"
<p><img src="https://user-images.githubusercontent.com/71399485/109642939-d9b5bb80-7b53-11eb-84de-fcef83fcb056.png" alt="Cat"></p>

paso 3 
  - Actualice el repositorio de apt:
    -sudo apt-get update
<p><img src="https://user-images.githubusercontent.com/71399485/109642977-e89c6e00-7b53-11eb-826f-2425505fbc00.png" alt="Cat"></p>

paso 4 
  - Instale Docker Engine - Community (la última versión de Docker) y containerd:
    - sudo apt-get install docker-ce docker-ce-cli containerd.io
<p><img src="https://user-images.githubusercontent.com/71399485/109643012-f651f380-7b53-11eb-8cee-14fbad8c95c6.png" alt="Cat"></p>
   
paso 5 
  - El servicio se iniciará automáticamente después de la instalación. Verifique el estado escribiendo:
    - sudo systemctl status docker
<p><img src="https://user-images.githubusercontent.com/71399485/109643052-02d64c00-7b54-11eb-86eb-7dd63482dd09.png" alt="Cat"></p>


Creamos un volumen: sanjoreva_mail_server

 -docker volume create volum_mail_server

Creamos el dominio sanjoreva.io
 -docker run -p 443:443 -e TZ=Europe/Andorra -v volum_mail_server:/data --name "sanjorevamailserver" -h "sanjoreva.io" -t analogic/poste.io

Entramos al firefox de inta por terminal con el comando
 -ssh 10.5.2.10 -X firefox
 -colocamos la ip: 172.17.0.2/admin (para crear una cuenta admin con el dominio admin@sanjoreva.io)
<p><img src="https://user-images.githubusercontent.com/71399485/109845371-58daea80-7c4d-11eb-8625-ec7265f2cb34.png"></p>
<p><img src="https://user-images.githubusercontent.com/71399485/109845616-a2c3d080-7c4d-11eb-8c5d-8d8c3ef4c458.png"></p>
 -En otra pestaña del firefox que abrimos en inta escribimos la siguiente ip: 172.17.0.2/webmail
 <p><img src="https://user-images.githubusercontent.com/71399485/109845710-b96a2780-7c4d-11eb-94ae-49342a902633.png"></p>
