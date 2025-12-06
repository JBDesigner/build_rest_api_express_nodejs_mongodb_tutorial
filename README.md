# REST API avec Express, Node.js et MongoDB

Une API REST simple pour gérer des abonnés (subscribers), construite avec Express.js et MongoDB.

## 🚀 Technologies utilisées

- **Node.js** - Environnement d'exécution JavaScript
- **Express.js** v5.2 - Framework web
- **MongoDB** - Base de données NoSQL
- **Mongoose** v9.0 - ODM pour MongoDB
- **Nodemon** - Rechargement automatique en développement
- **dotenv** - Gestion des variables d'environnement

## 📁 Structure du projet

```
├── models/
│   └── subscriber.js    # Modèle Mongoose pour les abonnés
├── routes/
│   └── subscribers.js   # Routes CRUD pour les abonnés
├── server.js            # Point d'entrée de l'application
├── route.rest           # Fichier de test des requêtes (REST Client)
├── package.json
└── .env                 # Variables d'environnement (à créer)
```

## 📋 Prérequis

- Node.js (v18 ou supérieur recommandé)
- MongoDB (local ou Atlas)

## ⚙️ Installation

1. **Cloner le repository**
   ```bash
   git clone https://github.com/JBDesigner/build_rest_api_express_nodejs_mongodb_tutorial.git
   cd build_rest_api_express_nodejs_mongodb_tutorial
   ```

2. **Installer les dépendances**
   ```bash
   npm install
   ```

3. **Configurer les variables d'environnement**
   
   Créer un fichier `.env` à la racine du projet :
   ```env
   DATABASE_URL=mongodb://localhost/subscribers
   ```

4. **Lancer le serveur en mode développement**
   ```bash
   npm run dev
   ```

   Le serveur sera accessible sur `http://localhost:3000`

## 📡 Endpoints de l'API

### Subscribers

| Méthode | Endpoint | Description |
|---------|----------|-------------|
| `GET` | `/subscribers` | Récupérer tous les abonnés |
| `GET` | `/subscribers/:id` | Récupérer un abonné par ID |
| `POST` | `/subscribers` | Créer un nouvel abonné |
| `PATCH` | `/subscribers/:id` | Mettre à jour un abonné |
| `DELETE` | `/subscribers/:id` | Supprimer un abonné |

### Exemples de requêtes

#### Créer un abonné
```http
POST http://localhost:4000/subscribers
Content-Type: application/json

{
    "name": "John Doe",
    "subscribedToChannel": "Tech Channel"
}
```

#### Mettre à jour un abonné
```http
PATCH http://localhost:4000/subscribers/:id
Content-Type: application/json

{
    "name": "Nouveau Nom"
}
```

## 📊 Modèle de données

### Subscriber

| Champ | Type | Requis | Description |
|-------|------|--------|-------------|
| `name` | String | ✅ | Nom de l'abonné |
| `subscribedToChannel` | String | ✅ | Chaîne à laquelle l'abonné est inscrit |
| `subscribeDate` | Date | ✅ | Date d'inscription (par défaut: date actuelle) |

## 🧪 Tester l'API

Vous pouvez utiliser :
- Le fichier `route.rest` avec l'extension [REST Client](https://marketplace.visualstudio.com/items?itemName=humao.rest-client) dans VS Code
- [Postman](https://www.postman.com/)
- [Insomnia](https://insomnia.rest/)
- cURL

## 📝 Scripts disponibles

| Commande | Description |
|----------|-------------|
| `npm run dev` | Lance le serveur avec nodemon (hot-reload) |

## 📄 Licence

ISC
