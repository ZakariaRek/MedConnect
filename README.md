# MediConnect

![MediConnect Logo](https://img.shields.io/badge/MediConnect-Healthcare%20Management-green)
![Next.js](https://img.shields.io/badge/Next.js-14-black)
![Node.js](https://img.shields.io/badge/Node.js-Express-green)
![MongoDB](https://img.shields.io/badge/MongoDB-Database-green)
![TypeScript](https://img.shields.io/badge/TypeScript-Language-blue)

## 📋 Description

**MediConnect** est une application web complète dédiée à la digitalisation de la gestion des dossiers médicaux et à la génération de rapports d'activités pour les unités de santé au travail. Développée pour le **Ministère de la Santé et de la Protection Sociale du Maroc**, cette solution vise à :

- 🏥 Améliorer l'efficacité de la gestion des dossiers médicaux
- ❌ Réduire les erreurs de saisie et de traitement
- 🔒 Assurer la sécurité et la confidentialité des données médicales
- 📊 Faciliter la génération de rapports d'activités

## 🚀 Fonctionnalités Principales

### 👥 Gestion des Utilisateurs
- **Authentification sécurisée** avec JWT
- **Gestion des rôles** : Administrateur, Médecin, Secrétaire
- **Profils utilisateurs** complets avec informations personnelles et professionnelles

### 🗂️ Gestion des Dossiers Médicaux
- **Création de dossiers** patients complets
- **Antécédents médicaux** familiaux et personnels
- **Antécédents professionnels** détaillés
- **Historique des vaccinations**
- **Premier examen médical** complet avec tous les appareils
- **Upload et gestion des scans** médicaux
- **Export PDF** automatisé des dossiers

### 🏥 Gestion du Matériel Médical
- **Inventaire** des équipements médicaux
- **Suivi de l'état** et de la disponibilité
- **Gestion opérationnelle** des dispositifs

### 📅 Visites Périodiques
- **Programmation** des visites de contrôle
- **Suivi médical** continu des patients
- **Historique** des consultations

### 📊 Rapports et Statistiques
- **Génération automatique** de rapports d'activités
- **Statistiques** sur les dossiers traités
- **Tableaux de bord** interactifs

## 🛠️ Technologies Utilisées

### Frontend
- **Next.js 14** - Framework React avec App Router
- **TypeScript** - Typage statique
- **Tailwind CSS** - Framework CSS utilitaire
- **React Hook Form** - Gestion des formulaires
- **Zod** - Validation des schémas
- **Zustand** - Gestion d'état
- **React PDF** - Génération de documents PDF
- **Recharts** - Graphiques et visualisations

### Backend
- **Node.js** - Runtime JavaScript
- **Express.js** - Framework web
- **MongoDB** - Base de données NoSQL
- **Mongoose** - ODM MongoDB
- **JWT** - Authentification par tokens
- **bcrypt** - Hachage des mots de passe
- **CORS** - Gestion des requêtes cross-origin

## 📁 Structure du Projet

```
MediConnect/
├── MediConnect/                 # Frontend Next.js
│   ├── app/                    # App Router Next.js 14
│   │   ├── (login)/           # Authentification
│   │   ├── main/              # Application principale
│   │   │   ├── dossierMedical/    # Gestion dossiers
│   │   │   ├── employe/           # Gestion employés
│   │   │   ├── materiel/          # Gestion matériel
│   │   │   └── visite/            # Visites périodiques
│   │   └── globals.css        # Styles globaux
│   ├── components/            # Composants réutilisables
│   │   ├── forms/            # Formulaires
│   │   ├── tables/           # Tableaux de données
│   │   ├── charts/           # Graphiques
│   │   └── shared/           # Composants partagés
│   ├── lib/                  # Utilitaires et configurations
│   └── api/                  # Fonctions API
└── mediconnect_server/        # Backend Node.js
    ├── models/               # Modèles Mongoose
    ├── routes/               # Routes Express
    ├── middleware.js         # Middlewares
    └── index.js              # Point d'entrée
```

## ⚙️ Installation et Configuration

### Prérequis
- Node.js >= 18.0.0
- MongoDB >= 5.0
- npm ou yarn

### 1. Cloner le Repository
```bash
git clone https://github.com/votre-username/mediconnect.git
cd mediconnect
```

### 2. Configuration Backend
```bash
cd mediconnect_server
npm install

# Créer le fichier .env
touch .env
```

**Contenu du fichier `.env` :**
```env
DATABASE_URL=mongodb://localhost:27017/mediconnect
TOKEN_SECRET=votre_secret_jwt_tres_securise
PORT=3001
```

**Démarrer le serveur backend :**
```bash
npm run dev
```

### 3. Configuration Frontend
```bash
cd ../MediConnect
npm install

# Démarrer le serveur de développement
npm run dev
```

### 4. Accéder à l'Application
- Frontend : `http://localhost:3000`
- Backend API : `http://localhost:3001`

## 👨‍⚕️ Utilisation

### Connexion
1. Accédez à `http://localhost:3000`
2. Connectez-vous avec vos identifiants (CIN + mot de passe)
3. L'interface s'adapte selon votre rôle :
   - **Admin** : Accès complet + gestion des employés
   - **Médecin** : Gestion des dossiers médicaux et du matériel
   - **Secrétaire** : Consultation des dossiers médicaux

### Gestion des Dossiers Médicaux
1. **Création d'un nouveau dossier** :
   - Informations personnelles du patient
   - Antécédents médicaux et professionnels
   - Vaccinations et rappels
   - Premier examen médical complet

2. **Consultation et modification** :
   - Liste complète des dossiers
   - Recherche et filtrage
   - Export PDF individuel

3. **Upload de documents** :
   - Scans médicaux par appareil
   - Images de résultats d'examens

### Gestion du Personnel
- **Ajout d'employés** avec rôles spécifiques
- **Modification des informations** personnelles et professionnelles
- **Gestion des accès** selon les responsabilités

## 🔐 Sécurité

- **Authentification JWT** avec tokens sécurisés
- **Hachage des mots de passe** avec bcrypt
- **Contrôle d'accès** basé sur les rôles
- **Validation des données** côté client et serveur
- **Protection CORS** configurée

## 📊 Base de Données

### Modèles Principaux

#### Utilisateur (User)
```javascript
{
  nom: String,
  prenom: String,
  cin: String,
  telephone: String,
  password: String, // Haché
  adresse: String,
  daten: Date,
  posteTravail: String,
  PPR: String,
  user_type: String // admin, medecin, secretaire
}
```

#### Dossier Médical
```javascript
{
  InfoPersonnel: { /* Informations patient */ },
  Antecedent_médicaux: { /* Antécédents familiaux et personnels */ },
  Antecedent_Professionnels: { /* Historique professionnel */ },
  Vaccination: [{ /* Historique vaccinal */ }],
  PremierExam: { /* Examen médical complet */ },
  visites: [ObjectId] // Références aux visites
}
```

## 🚀 Déploiement

### Production
1. **Build du frontend** :
```bash
cd MediConnect
npm run build
```

2. **Configuration de production** :
   - Variables d'environnement de production
   - Base de données MongoDB Atlas (recommandé)
   - Serveur web (Nginx + PM2)

3. **Déploiement recommandé** :
   - **Frontend** : Vercel, Netlify ou serveur statique
   - **Backend** : VPS avec PM2, Heroku, ou cloud provider
   - **Base de données** : MongoDB Atlas

## 📈 Roadmap

- [ ] **Module de télémédecine**
- [ ] **Application mobile** (React Native)
- [ ] **Intégration avec équipements médicaux**
- [ ] **Système de notifications** push
- [ ] **API REST** complète pour intégrations tierces
- [ ] **Dashboard analytique** avancé
- [ ] **Système de rendez-vous** en ligne

## 👥 Contribution

1. Fork le projet
2. Créez une branche feature (`git checkout -b feature/nouvelle-fonctionnalite`)
3. Committez vos changements (`git commit -m 'Ajout nouvelle fonctionnalité'`)
4. Push vers la branche (`git push origin feature/nouvelle-fonctionnalite`)
5. Ouvrez une Pull Request

## 📞 Support

Pour toute question ou support technique :
- **Email** : support@mediconnect.ma
- **Documentation** : [Wiki du projet](link-to-wiki)
- **Issues** : [GitHub Issues](link-to-issues)

## 📄 Licence

Ce projet est développé dans le cadre d'un stage au **Ministère de la Santé et de la Protection Sociale du Maroc**.

---

**Développé avec ❤️ pour la digitalisation du système de santé marocain**

*Période de développement : Mars 2024 - Juin 2024*
