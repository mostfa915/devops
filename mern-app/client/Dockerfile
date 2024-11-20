# Étape 1 : Utiliser l'image Node.js pour construire l'application
FROM node:16 AS build

# Définir le répertoire de travail
WORKDIR /app

# Copier le fichier package.json et package-lock.json
COPY package*.json ./

# Installer les dépendances
RUN npm install

# Copier le reste du code source de l'application
COPY . .

# Construire l'application React pour la production
RUN npm run build

# Étape 2 : Utiliser Nginx pour servir l'application construite
FROM nginx:alpine

# Copier le build de React dans le répertoire de Nginx
COPY --from=build /app/build /usr/share/nginx/html

# Exposer le port 80
EXPOSE 80

# Démarrer Nginx (par défaut, Nginx est configuré pour écouter sur le port 80)
CMD ["nginx", "-g", "daemon off;"]

