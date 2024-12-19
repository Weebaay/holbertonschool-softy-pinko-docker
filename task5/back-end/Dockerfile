# Utiliser l'image Ubuntu la plus récente
FROM ubuntu:latest

# Mise à jour et installation de Python3 et pip3
RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y python3 python3-pip

# Résolution de l'erreur "This environment is externally managed"
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

# Installation de Flask via pip3
RUN pip3 install flask

# Installer Flask et Flask-CORS
RUN pip3 install flask flask-cors

# Définir le répertoire de travail
WORKDIR /app

# Copier le fichier api.py dans l'image
COPY ./api.py /app/api.py

# Commande par défaut : lancer le serveur Flask
CMD ["python3", "api.py"]