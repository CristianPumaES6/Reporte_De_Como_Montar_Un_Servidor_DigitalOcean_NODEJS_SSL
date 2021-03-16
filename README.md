# Reporte_De_Como_Montar_Un_Servidor_DigitalOcean_NODEJS_SSL

Empecemos

Primero Montaremos un servidor,

Existen 2 tipos de servidores hardware y software, el hardware nos lo proveera Digital Ocean o algun otra empresa de servidores virtuales privados.

Ahora tal vez ustedes quieran montar el servidor desde sus laptop o pc o celular, nos evitamos todo eso con digital ocean, el servidor solo cuesta 5 dolares al mes.
Cosa que sorprende.

![image](https://user-images.githubusercontent.com/29841048/111059023-75063500-8460-11eb-81b2-0e04a8990d5c.png)

Limpio! 

Empezamos!


Entes no habia eso O.o? ?? ? ?

Supongo que algun dia los contratare o tal vez no :'D

![image](https://user-images.githubusercontent.com/29841048/111059489-0f1bac80-8464-11eb-8d99-26fe66dd5102.png)

![image](https://user-images.githubusercontent.com/29841048/111059567-9a953d80-8464-11eb-8773-9f6a71c55999.png)
1 TB de transferencia 25GB de almacenamiento, 1 CPU.

La contraseña estaba dificil 


Ya tenemos nuestro hardware funcionando corrrectamente.

Abrimos el putty para conectarnos con nuestra maquina remotamente.

Accedemos Root y nuestro password que colocamos anterioremente.


Ya tenemos instalado
- curl
- node
- git
- habilitamos los puestos
- instalamos NGinx
- Verificamos si la ip tiene un index.html

-




YA TENEMOS CONTROL DEL SERVIDOR

 Escojere la version 12 por que estoy trabajando en mi local la version 12.

hemos estado habilitando puertos.

====================000

ES UN NUEVO DIA LO HAREMOS DE NUEVO:

COnstraseña
Cris1996Tian

Creamos el droper

entramos desde el putty con nuestro user root y constraseña.

 sudo apt-get update
 
sudo apt -y install curl dirmngr apt-transport-https lsb-rele  

curl -sL https://deb.nodesource.com/setup_12.x | sudo bash

sudo apt-get update && sudo apt-get install yarn

sudo apt update


// Ahora instalamos node.
sudo apt-get install nodejs

sudo apt-get install git

sudo ufw status

sudo ufw allow 'Nginx HTTP'

sudo ufw status

udo ufw allow 22

sudo ufw allow ftp

sudo ufw allow 21/tcp

sudo ufw enable

// Al habilitar la url que aputnen a nuestro servidor por defecto se redireccionara a hmtl.
// lo que haremos ahora sera fraccionar los dominios
https://github.com/mayratc/AWS_Production/blob/master/3.instalar-ngnix.md

sudo mkdir -p /var/www/labcode.site/

// y dnetro le pones mos uindex.hmtl

sudo chown -R $USER:$USER /var/www/

sudo chmod -R 755 /var/www/

// Nos vamos al siquiente directorio

:/etc/nginx/sites-available#


// COpiamos el archivo por defecto
 cp default labcode.site




https://www.digitalocean.com/community/tutorials/how-to-set-up-nginx-server-blocks-virtual-hosts-on-ubuntu-16-04
sudo systemctl restart nginx

verificamos la ip de la pagina desde chrome 

Si esta levantado en nuestr ip puerto : 80

// Modificamos nuestro sitio
// sudo nano /etc/nginx/sites-available/labcode.site
// nos ubicamos en /etc/nginx/sites-available
cp default labcode.site

sudo nano labcode.site

// Hacemos esto para generar el enabled

sudo ln -s /etc/nginx/sites-available/labcode.site /etc/nginx/sites-enabled/



sudo service nginx restart



// reset para volver a probar 
rm /etc/nginx/sites-enabled/labcode.site

// Como convertir nuestro proyecto de nestjs a production.
nest start crea un directorio dir

// Copiamos el directorio 
y lo pegamos en el directorio backend dentro de nuestro proyecto brach production
lo probamos

npm install 

node main.js
Deeria levantar todo en verde sin errores.

si es asi hacemos commit, y pusheamos

En el server desde el directorio del proyecto

var / www/ Dominio / proyecto

git clone -b production URL

npm install

node mainjs

si levanta ok ponemos
sudo npm install pm2@latest -g

pm2 start main.js

y estara deployado en nuesto pm2

nos vamos a ngnix a modificar con los sigjuientes datos
root@Production:/etc/nginx/sites-available# sudo nano labcode.site

server {
    listen 80;
    listen [::]:80;

    server_name labcode.site www.labcode.site;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}



rm /etc/nginx/sites-enabled/labcode.site



sudo ln -s /etc/nginx/sites-available/labcode.site /etc/nginx/sites-enabled/



sudo service nginx restart


Y se muestra la Ip cuando se logean como labcode.

ahora protocolo https

sudo apt install certbot python3-certbot-nginx

sudo systemctl reload nginx

sudo ufw allow 'Nginx Full'
sudo ufw delete allow 'Nginx HTTP'

sudo certbot --nginx -d example.com -d www.example.com

Select the appropriate number [1-2] then [enter] (press 'c' to cancel):
2


cosnultamos cerbor

sudo systemctl status certbot.timer

sudo systemctl reload nginx y tenemos https
https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04-es



ufw status verbose
80 22 21




