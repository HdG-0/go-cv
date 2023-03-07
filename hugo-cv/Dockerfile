# Utilisation d'une image de base Alpine Linux légère
FROM alpine:latest

# Installation des dépendances nécessaires pour Hugo
RUN apk update && \
    apk add hugo

# Copie des fichiers de notre projet dans le conteneur
COPY . /app

# Exposition du port 2000 pour l'accès au site Hugo
EXPOSE 1313

# Définition du répertoire de travail dans le conteneur
WORKDIR /app

# Génération du site Hugo lors de la création de l'image
RUN hugo

# Commande pour démarrer le serveur Hugo
CMD ["hugo", "serve", "--noHTTPCache", "--appendPort=false", "--bind=0.0.0.0", "--baseURL=/","--environment", "production"]