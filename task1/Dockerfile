# Utiliser l'image de base Ubuntu la plus récente
FROM ubuntu:latest

# Mettre à jour et installer python3, pip3
RUN apt-get update && apt-get upgrade -y && \
    apt-get install -y python3 python3-pip

# Supprimer les restrictions d'installation de paquet python
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED

# Installer Flask avec pip3
RUN pip3 install flask

# Définir le répertoire de travail à /app
WORKDIR /app

# Copier le fichier api.py dans le conteneur
COPY ./api.py /app/api.py

# Exposer le port 5252
EXPOSE 5252

# Lancer l'application Flask
CMD ["python3", "api.py"]