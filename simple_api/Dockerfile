# Utilisation de l'image Python 3.8 comme base
FROM python:3.8-buster

# Mainteneur de l'image
LABEL maintainer="Jean <zacharia.sidibe@univ-thies.sn>"

# Définition du répertoire de travail
WORKDIR /

# Copier le fichier requirements.txt pour installer les dépendances
COPY requirements.txt /

# Mise à jour du système et installation des prérequis
RUN apt update -y && apt install -y python-dev python3-dev libsasl2-dev libldap2-dev libssl-dev \
    && pip3 install -r /requirements.txt

# Copier le code source de l'API
COPY . /

# Définition du volume pour stocker les données persistantes
VOLUME /data

# Exposition du port de l'API
EXPOSE 5000

# Commande de démarrage de l'API
CMD ["python3", "./student_age.py"]
