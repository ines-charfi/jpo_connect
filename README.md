# 📚 Documentation du Projet - Plateforme de Gestion des Journées Portes Ouvertes (JPO)

---

## 🎯 Objectif du projet

Cette plateforme permet aux futurs étudiants et à leurs parents de s’inscrire aux Journées Portes Ouvertes (JPO) organisées par La Plateforme dans plusieurs villes (Marseille, Cannes, Martigues, Paris). Elle offre également un tableau de bord complet pour l’équipe marketing afin de gérer les événements, les inscriptions, les commentaires et les rôles utilisateurs.

---

## 🗂️ Structure des dossiers

laplateforme-jpo/
├── backend/ # Backend PHP natif (API REST)
│ ├── api/ # Points d'entrée API (endpoints)
│ │ ├── auth.php # Authentification (login)
│ │ ├── register.php # Inscription utilisateur
│ │ ├── jpo.php # Gestion des JPO (liste, détail)
│ │ ├── user_events.php # Gestion des inscriptions/désinscriptions
│ │ ├── admin.php # API pour dashboard admin/modération
│ │ └── ... # Autres endpoints API
│ ├── includes/ # Fonctions utilitaires et constantes
│ │ ├── roles.php # Gestion des rôles et permissions
│ │ ├── mail.php # Fonction d’envoi d’emails (PHPMailer)
│ │ └── ...
│ ├── config.php # Configuration de la base de données et autres
│ ├── db.php # Connexion PDO à la base de données
│ └── schema.sql # Script SQL de création de la base de données
│
├── frontend/ # Frontend ReactJS
│ ├── public/ # Fichiers statiques (index.html, favicon, etc.)
│ ├── src/
│ │ ├── components/ # Composants réutilisables React
│ │ │ ├── Header.jsx # Barre de navigation
│ │ │ ├── Footer.jsx # Pied de page
│ │ │ ├── Login.jsx # Formulaire de connexion
│ │ │ ├── Register.jsx # Formulaire d’inscription
│ │ │ ├── JPOList.jsx # Liste des JPO
│ │ │ ├── JPOItem.jsx # Détail d’une JPO avec inscription
│ │ │ ├── UserEvents.jsx # Liste des inscriptions de l’utilisateur
│ │ │ ├── AdminDashboard.jsx # Dashboard admin/modération
│ │ │ ├── ProtectedRoute.jsx # Gestion des routes sécurisées
│ │ │ └── ...
│ │ ├── pages/ # Pages React (assemblage de composants)
│ │ │ ├── HomePage.jsx # Page d’accueil
│ │ │ ├── LoginPage.jsx # Page de connexion
│ │ │ ├── RegisterPage.jsx# Page d’inscription
│ │ │ ├── EventsPage.jsx # Page liste des événements
│ │ │ ├── UserEventsPage.jsx # Page des inscriptions utilisateur
│ │ │ ├── ProfilePage.jsx # Profil utilisateur
│ │ │ ├── AdminPage.jsx # Page dashboard admin
│ │ │ └── ...
│ │ ├── App.jsx # Composant principal avec routage
│ │ ├── App.css # Styles globaux
│ │ └── index.js # Point d’entrée React
│ ├── package.json # Dépendances frontend
│ └── ...
│
└── README.md # Cette documentation

---

## ⚙️ Installation et lancement

### Prérequis

- PHP 7.4+ avec PDO et extensions nécessaires
- MySQL ou MariaDB
- Node.js et npm (pour ReactJS)

### Étapes

1. **Base de données**  
   - Importer le fichier `backend/laplateforme_jpo.sql` dans votre serveur MySQL pour créer la base et les tables.

2. **Configuration backend**  
   - Modifier `backend/config.php` avec vos identifiants de base de données.

3. **Dépendances frontend**
   
4. **Lancer le backend** (depuis le dossier backend)  

5. **Lancer le frontend** (depuis le dossier frontend)  

6. **Accéder à l’application**  
Ouvrir dans un navigateur :  
- Frontend : `http://localhost:3000`  
- Backend API : `http://localhost:8000/api/...`

---

## 🔐 Gestion des rôles

| Rôle       | Permissions principales                                    |
|------------|------------------------------------------------------------|
| Admin      | Gérer les JPO, modérer commentaires, gérer utilisateurs, voir statistiques |
| Manager    | Gérer les JPO, modérer commentaires, voir statistiques     |
| Employee   | Voir les JPO, gérer inscriptions, consulter statistiques    |
| Utilisateur| S’inscrire/désinscrire aux JPO, laisser des commentaires   |

Les rôles sont définis dans `backend/includes/roles.php` et vérifiés dans les API.

---

## 📧 Envoi d’emails

La fonction d’envoi d’emails est centralisée dans `backend/includes/mail.php` et utilise PHPMailer. Elle sert notamment pour les rappels d’événements.

---

## 📄 Fonctionnalités principales

- Inscription / connexion utilisateur  
- Consultation et recherche des JPO  
- Inscription / désinscription aux événements  
- Gestion des commentaires et modération  
- Tableau de bord complet pour l’équipe marketing (gestion des JPO, statistiques, modération)  
- Gestion des rôles et permissions  
- Interface responsive avec ReactJS  

---

## 🤝 Contribution

N’hésitez pas à contribuer, signaler des bugs ou suggérer des améliorations via les issues GitHub.



*Merci d’utiliser cette plateforme pour faciliter la gestion des Journées Portes Ouvertes !*  

