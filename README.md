# django-docker-composer
simple PROJECT PART 1

https://webdevblog.ru/kak-ispolzovat-django-postgresql-i-docker/

 | root@gorno-ess ~ $ cat /etc/nginx/sites-enabled/upload.conf 
server {
  listen 80 ;
 # listen [::]:80 default_server;
  server_name dfm.ru www.dfm.ru;
  root /var/www/dfm;
 # location ~ /.well-known {
 #   allow all;
 #   try_files $uri $uri/;
 # }

#  location /robots.txt {
#    alias /var/www/dfm/robots.txt;
#  }

#  location /api {
    #proxy_pass http://127.0.0.1:8000/api;
 #   proxy_pass http://127.0.0.1:1337/api;
 # }
  
  location / {
    proxy_redirect     off;

    proxy_set_header   Host                 $host;
    proxy_set_header   X-Real-IP            $remote_addr;
    proxy_set_header   X-Forwarded-For      $proxy_add_x_forwarded_for;
    proxy_set_header   X-Forwarded-Proto    $scheme;

   # proxy_pass http://localhost:8000;
    proxy_pass http://localhost:1337;
  }

#    listen 443 ssl; # managed by Certbot
#ssl_certificate /etc/letsencrypt/live/dfm-dev.apptimizm.pro/fullchain.pem; # managed by Certbot
#ssl_certificate_key /etc/letsencrypt/live/dfm-dev.apptimizm.pro/privkey.pem; # managed by Certbot
 #   include /etc/letsencrypt/options-ssl-nginx.conf; # managed by Certbot
 #   ssl_dhparam /etc/letsencrypt/ssl-dhparams.pem; # managed by Certbot

 #   if ($scheme != "https") {
  #      return 301 https://$host$request_uri;
   # } # managed by Certbot

}
