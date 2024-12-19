# Utiliser l'image Nginx la plus récente
FROM nginx:latest

# Copier les fichiers du front-end dans le répertoire Nginx
COPY ./softy-pinko-front-end /var/www/html/softy-pinko-front-end

# Copier la configuration Nginx
COPY ./softy-pinko-front-end.conf /etc/nginx/conf.d/default.conf