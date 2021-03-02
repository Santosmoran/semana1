# semana1
creamos un volumen: sanjoreva_mail_server
docker volume create volum_mail_server

creamos el dominio sanjoreva.io
docker run -p 443:443 -e TZ=Europe/Andorra -v volum_mail_server:/data --name "sanjorevamailserver" -h "sanjoreva.io" -t analogic/poste.io

entramos al firefox de inta por terminal con el comando
ssh 10.5.2.10 -X firefox
<p><img src="https://user-images.githubusercontent.com/71399485/109640295-9279fb80-7b50-11eb-9c0a-6673063723de.png" alt="Cat"></p>
