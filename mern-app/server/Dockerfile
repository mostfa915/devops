# Étape 1 : Utiliser l'image Node.js pour le backend Express
FROM node:lts-alpine

# Définir le répertoire de travail
WORKDIR /usr/src/app

# Copier les fichiers package.json et package-lock.json pour installer les dépendances
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier tous les fichiers du backend Express dans l'image
COPY . .

# Exposer le port sur lequel l'application va fonctionner (par défaut, Express écoute sur le port 3000)
EXPOSE 3000

# Démarrer l'application Express
CMD ["npm", "start"]
