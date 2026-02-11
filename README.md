# 🔐 UniLogi - Version Sécurisée

## 📦 Package de correction et sécurisation

Ce package contient tous les fichiers nécessaires pour corriger et sécuriser votre application UniLogi.

---

## 📂 Structure du package

```
unilogi-securise/
├── backend/
│   ├── server.js                 # Nouveau serveur sécurisé
│   ├── package.json              # Dépendances mises à jour
│   ├── .env.example              # Configuration exemple
│   └── generate-ssl.sh           # Script SSL
├── frontend/
│   └── Login.jsx                 # Fichier de login corrigé
├── docs/
│   ├── GUIDE_INSTALLATION.md     # Guide complet
│   └── CORRECTIONS_DETAILLEES.md # Détails des corrections
├── install.ps1                   # Script d'installation auto
└── README.md                     # Ce fichier
```

---

## 🚀 Installation Rapide

### Option 1: Installation automatique (Windows PowerShell)

```powershell
# Exécuter le script d'installation
.\install.ps1
```

### Option 2: Installation manuelle

#### 1. Backend

```bash
cd C:\Users\RN-Re\Desktop\unilogi-main\unilogi-main\backend

# Copier les fichiers
copy /path/to/unilogi-securise/backend/server.js ./server.js
copy /path/to/unilogi-securise/backend/package.json ./package.json
copy /path/to/unilogi-securise/backend/.env.example ./.env

# Installer les dépendances
npm install

# IMPORTANT: Modifier JWT_SECRET dans .env
```

#### 2. Frontend

```bash
cd C:\Users\RN-Re\Desktop\unilogi-main\unilogi-main\frontend

# Copier le fichier corrigé
copy /path/to/unilogi-securise/frontend/Login.jsx ./src/pages/Login.jsx
```

#### 3. Démarrage

**Terminal 1 - Backend:**
```bash
cd backend
node server.js
```

**Terminal 2 - Frontend:**
```bash
cd frontend
npm run dev
```

---

## ✅ Problèmes corrigés

1. ✅ **Impossible de créer un compte** (URL API incorrecte)
2. ✅ **Erreur CORS** (Cross-Origin bloqué)
3. ✅ **Pas de sécurité** (ajout de 10 couches de sécurité)

---

## 🔒 Sécurité ajoutée

- ✅ Helmet (Headers HTTP sécurisés)
- ✅ CORS configuré correctement
- ✅ Rate Limiting (protection force brute)
- ✅ Validation des données (email, password)
- ✅ Hashing bcrypt renforcé (coût 12)
- ✅ JWT avec expiration (7 jours)
- ✅ HTTPS disponible (certificats SSL)
- ✅ Sanitization des inputs (protection XSS)
- ✅ Protection des données personnelles
- ✅ Gestion d'erreurs améliorée

---

## 📖 Documentation

- **Guide d'installation complet:** `docs/GUIDE_INSTALLATION.md`
- **Détails des corrections:** `docs/CORRECTIONS_DETAILLEES.md`

---

## 🧪 Tester l'application

1. Ouvrez http://localhost:5173
2. Cliquez sur "S'inscrire"
3. Créez un compte avec:
   - Email valide
   - Mot de passe: min. 8 caractères, 1 majuscule, 1 minuscule, 1 chiffre
4. Connectez-vous
5. Explorez l'application !

---

## 🛡️ Checklist de sécurité (Production)

Avant de déployer en production:

- [ ] Changer le JWT_SECRET (64+ caractères aléatoires)
- [ ] Activer HTTPS avec un vrai certificat
- [ ] Configurer les origines CORS pour votre domaine
- [ ] Utiliser une vraie base de données
- [ ] Activer les logs de sécurité
- [ ] Configurer un reverse proxy (Nginx)
- [ ] Activer le monitoring
- [ ] Configurer des backups automatiques

---

## 🐛 Dépannage

### Le backend ne démarre pas
- Vérifiez que Node.js est installé: `node --version`
- Vérifiez que les dépendances sont installées: `npm install`
- Vérifiez les logs d'erreur

### "Failed to fetch" dans le navigateur
- Vérifiez que le backend tourne sur le port 3001
- Vérifiez `frontend/src/config.js` (API_URL doit être http://localhost:3001)
- Ouvrez F12 → Console pour voir l'erreur exacte

### Erreur CORS
- Vérifiez que les origines sont bien configurées dans le backend
- Redémarrez le serveur backend

### Rate limit dépassé
- Attendez 15 minutes
- OU redémarrez le serveur backend

---

## 📞 Support

Si vous rencontrez des problèmes:

1. Consultez `docs/GUIDE_INSTALLATION.md`
2. Consultez `docs/CORRECTIONS_DETAILLEES.md`
3. Vérifiez les logs du serveur backend
4. Vérifiez la console du navigateur (F12)

---

## 🎉 Félicitations !

Votre application UniLogi est maintenant sécurisée et fonctionnelle !

**Développé avec ❤️ et 🔐**

---

## 📝 Changelog

### Version 2.0.0 (2024)
- ✅ Correction du problème d'inscription/connexion
- ✅ Ajout de 10 couches de sécurité
- ✅ Support HTTPS
- ✅ Documentation complète

### Version 1.0.0 (Originale)
- Application de base
