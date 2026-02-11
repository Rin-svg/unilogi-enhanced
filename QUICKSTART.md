# 🚀 Guide de Démarrage Rapide - UniLogi Enhanced

## 📦 Ce que vous avez reçu

Votre projet UniLogi a été amélioré avec toutes les fonctionnalités demandées :

✅ **Animation de chargement** avec le nom UniLogi
✅ **Sécurité renforcée** - bcrypt + JWT + variables d'environnement
✅ **Messagerie** - Bouton "Discuter avec le bailleur" sur chaque annonce
✅ **Chatbot IA** - Assistant virtuel pour les étudiants (Anthropic Claude)
✅ **Recherche IA** - API préparée pour recommandations intelligentes
✅ **Tous les boutons fonctionnels**

## 📁 Structure des fichiers

```
unilogi-enhanced/
├── README.md                    ← Lisez-moi en premier !
├── DEPLOYMENT.md                ← Guide de déploiement en production
├── FEATURES.md                  ← Documentation détaillée des fonctionnalités
├── .gitignore                   ← Protection des fichiers sensibles
│
├── backend/
│   ├── server-enhanced.js       ← Nouveau serveur avec IA et sécurité
│   ├── server.js                ← Ancien serveur (backup)
│   ├── .env.example             ← Template de configuration
│   └── package.json             ← Dépendances mises à jour
│
└── frontend/
    ├── src/
    │   ├── components/
    │   │   ├── LoadingScreen.jsx    ← Animation de chargement
    │   │   ├── AIChatbot.jsx        ← Chatbot IA flottant
    │   │   └── LandlordChat.jsx     ← Chat avec bailleur
    │   ├── pages/
    │   │   ├── Landing.jsx          ← Page d'accueil avec animation
    │   │   └── ApartmentDetails.jsx ← Bouton "Discuter" ajouté
    │   ├── config.js                ← Configuration centralisée
    │   └── App.jsx                  ← Chatbot ajouté partout
    ├── .env.example                 ← Variables frontend
    └── package.json
```

## ⚡ Installation Rapide (5 minutes)

### Étape 1 : Extraire le projet

```bash
unzip unilogi-enhanced.zip
cd unilogi-enhanced
```

### Étape 2 : Configurer le Backend

```bash
cd backend

# Installer les dépendances
npm install

# Créer le fichier de configuration
cp .env.example .env
```

**Éditer le fichier `.env`** :

```env
PORT=3000
JWT_SECRET=generer_un_secret_complexe_ici
ANTHROPIC_API_KEY=votre_cle_anthropic_ici
EMAIL_HOST=smtp.ethereal.email
EMAIL_USER=votre_email
EMAIL_PASSWORD=votre_mot_de_passe
FRONTEND_URL=http://localhost:5173
```

### Étape 3 : Configurer le Frontend

```bash
cd ../frontend

# Installer les dépendances
npm install
```

### Étape 4 : Lancer l'Application

**Terminal 1 - Backend :**
```bash
cd backend
npm start
```

Vous devriez voir :
```
🚀 Serveur backend UniLogi démarré sur http://localhost:3000
📧 Configuration email: smtp.ethereal.email
🤖 IA Anthropic: Configurée
🔒 Sécurité: bcrypt + JWT activés
```

**Terminal 2 - Frontend :**
```bash
cd frontend
npm run dev
```

Vous devriez voir :
```
  VITE v5.x.x  ready in xxx ms

  ➜  Local:   http://localhost:5173/
```

**C'est tout ! 🎉**

Ouvrez http://localhost:5173/ dans votre navigateur.

## 🎯 Tester les Nouvelles Fonctionnalités

### 1. Animation de Chargement

- Allez sur http://localhost:5173/
- Vous verrez l'animation avec le logo UniLogi
- La barre de progression remplit à 100%
- La page principale apparaît ensuite

### 2. Sécurité

- **Inscription** : Le mot de passe est automatiquement hashé avec bcrypt
- **Connexion** : Un token JWT est généré
- **Routes protégées** : Essayez d'accéder à /home sans être connecté

### 3. Chatbot IA

**IMPORTANT** : Pour que le chatbot fonctionne, vous DEVEZ :

1. Obtenir une clé API Anthropic :
   - Allez sur https://console.anthropic.com/
   - Créez un compte
   - Générez une clé API
   - Mettez-la dans `backend/.env` :
   ```env
   ANTHROPIC_API_KEY=sk-ant-api03-xxxxx
   ```

2. Tester le chatbot :
   - Connectez-vous à l'application
   - Cliquez sur le bouton flottant en bas à droite
   - Posez une question comme "Comment trouver un logement ?"

### 4. Messagerie avec Bailleur

1. Connectez-vous
2. Cliquez sur n'importe quelle annonce
3. En bas, vous verrez deux boutons : **Discuter** et **Appeler**
4. Cliquez sur **Discuter**
5. Une fenêtre de chat s'ouvre
6. Envoyez un message au propriétaire

## 🔑 Obtenir les Clés API

### Anthropic (pour le Chatbot IA)

1. Allez sur https://console.anthropic.com/
2. **Sign Up** → Créez un compte
3. Menu **API Keys** → **Create Key**
4. Copiez la clé qui commence par `sk-ant-api03-`
5. Collez dans `backend/.env` :
   ```env
   ANTHROPIC_API_KEY=sk-ant-api03-xxxxx
   ```

**Note** : Anthropic offre des crédits gratuits pour commencer.

### Google Maps (optionnel pour l'instant)

1. Allez sur https://console.cloud.google.com/
2. Créez un projet
3. Activez les APIs :
   - Maps JavaScript API
   - Places API
   - Geocoding API
4. Générez une clé API
5. Ajoutez dans `backend/.env` :
   ```env
   GOOGLE_MAPS_API_KEY=AIzaxxxxx
   ```

### Email (pour développement)

Pour le développement, utilisez **Ethereal Email** (gratuit, pas besoin de compte) :

1. Allez sur https://ethereal.email/
2. Cliquez sur **Create Ethereal Account**
3. Copiez les credentials générés
4. Collez dans `backend/.env` :
   ```env
   EMAIL_HOST=smtp.ethereal.email
   EMAIL_PORT=587
   EMAIL_USER=xxx@ethereal.email
   EMAIL_PASSWORD=xxxxxxxxx
   ```

Les emails ne sont pas vraiment envoyés, mais vous pouvez les voir dans les logs du serveur.

## 🐛 Dépannage

### Le backend ne démarre pas

**Erreur** : `Error: Cannot find module 'dotenv'`

**Solution** :
```bash
cd backend
npm install
```

### Le chatbot ne répond pas

**Erreur** : Console montre "Erreur IA Chatbot"

**Cause** : Clé API Anthropic manquante ou invalide

**Solution** :
1. Vérifiez que `ANTHROPIC_API_KEY` est dans `backend/.env`
2. Vérifiez que la clé commence par `sk-ant-api03-`
3. Redémarrez le serveur backend

### L'animation de chargement ne s'affiche pas

**Cause** : Cache du navigateur

**Solution** :
- Ctrl + Shift + R (Windows/Linux)
- Cmd + Shift + R (Mac)

### Les messages ne s'enregistrent pas

**Cause** : La base de données est en mémoire (redémarre à chaque fois)

**Solution** : Pour la production, suivez DEPLOYMENT.md pour configurer MongoDB

## 📚 Prochaines Étapes

1. **Testez toutes les fonctionnalités** localement
2. **Lisez FEATURES.md** pour comprendre le code
3. **Configurez les clés API** pour activer l'IA
4. **Personnalisez** l'apparence selon vos besoins
5. **Déployez en production** avec DEPLOYMENT.md

## 🎓 Ressources d'Apprentissage

### Documentation

- `README.md` - Vue d'ensemble et installation
- `FEATURES.md` - Détails techniques des fonctionnalités
- `DEPLOYMENT.md` - Déploiement en production

### Composants Clés

- `LoadingScreen.jsx` - Animation de chargement (facile à personnaliser)
- `AIChatbot.jsx` - Chatbot IA (modificable pour d'autres cas d'usage)
- `LandlordChat.jsx` - Système de messagerie (réutilisable)
- `server-enhanced.js` - Backend sécurisé (production-ready)

### Tutoriels Recommandés

1. **bcrypt** : https://github.com/kelektiv/node.bcrypt.js
2. **JWT** : https://jwt.io/introduction
3. **Anthropic Claude** : https://docs.anthropic.com/
4. **React** : https://react.dev/

## 💡 Conseils

### Développement

- **Toujours** utiliser `.env` pour les secrets
- **Jamais** commiter le fichier `.env`
- **Tester** en local avant de déployer
- **Lire** les logs du backend pour débugger

### Production

- **Suivre** DEPLOYMENT.md étape par étape
- **Configurer** HTTPS obligatoirement
- **Utiliser** MongoDB au lieu de la mémoire
- **Monitorer** l'application avec PM2

### Sécurité

- **Générer** un JWT_SECRET unique et complexe
- **Ne jamais** partager vos clés API
- **Activer** le rate limiting en production
- **Restreindre** les clés API Google

## 🆘 Besoin d'Aide ?

Si vous rencontrez un problème :

1. **Vérifiez** les logs du backend et frontend
2. **Consultez** FEATURES.md pour la documentation
3. **Recherchez** l'erreur dans Google
4. **Créez** une issue GitHub avec :
   - Description du problème
   - Messages d'erreur
   - Étapes pour reproduire

## ✅ Checklist Avant Production

- [ ] Toutes les dépendances installées (`npm install`)
- [ ] Fichier `.env` créé et configuré
- [ ] Clé API Anthropic obtenue et configurée
- [ ] JWT_SECRET généré et unique
- [ ] Application testée localement
- [ ] Toutes les fonctionnalités marchent
- [ ] .gitignore configuré (ne pas commiter .env)
- [ ] Documentation lue (README, FEATURES, DEPLOYMENT)
- [ ] Backup du code fait
- [ ] Prêt pour le déploiement !

## 🎉 Félicitations !

Vous avez maintenant une application UniLogi complète avec :
- ✅ Sécurité de niveau production
- ✅ Intelligence artificielle intégrée
- ✅ Système de messagerie
- ✅ Interface utilisateur moderne
- ✅ Documentation complète

**Bonne chance avec votre projet ! 🚀**

---

*Dernière mise à jour : Février 2026*
*Version : 2.0.0*
