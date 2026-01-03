# 📋 CAHIER DES CHARGES - ÉVOLUTION PLATEFORME E-LEARNING
## Projet : Corporis Academia - De la V1 vers la V2

---

# 📌 CONTEXTE DU PROJET

## Présentation

**Corporis Academia** est une plateforme e-learning dédiée aux étudiants en médecine (PASS/LASS) et Terminale. La plateforme actuelle (V1) est fonctionnelle et en production. Nous souhaitons la faire évoluer vers une V2 beaucoup plus complète.

## Objectif

Obtenir une estimation du coût et du temps de développement pour faire évoluer la plateforme de la V1 (existante) vers la V2 (souhaitée).

---

# 🏠 VERSION 1 - ÉTAT ACTUEL

## 1. Architecture Générale Actuelle

### Stack Technique
- **Frontend** : React + TypeScript + Vite
- **Backend** : Node.js + Express + TypeScript
- **Base de données** : PostgreSQL avec Prisma ORM
- **Conteneurisation** : Docker Compose
- **Hébergement** : VPS

### Applications
| Application | Description |
|-------------|-------------|
| Client Web | Interface étudiant |
| Admin Dashboard | Interface administration |
| Serveur API | Backend REST |

## 2. Fonctionnalités Actuelles V1

### 🔐 Authentification
- Inscription avec formulaire multi-étapes (nom, prénom, email, mot de passe, date de naissance)
- Choix du statut : PASS, LASS ou Terminale
- Connexion par email/mot de passe
- Connexion Google OAuth
- Réinitialisation de mot de passe par email
- Gestion de session avec tokens JWT

### 📚 Contenu Éducatif
- **Matières** : Liste de matières avec logos (ex: Anatomie, Biochimie, etc.)
- **Séances/Chapitres** : Chaque matière contient plusieurs séances
- **Vidéos de cours** : Vidéos hébergées sur Vimeo intégrées dans la plateforme
- **Fiches PDF** : Documents PDF téléchargeables par séance
- **Objectifs pédagogiques** : Liste d'objectifs par séance

### 💪 Exercices & QCM
- QCM à choix multiples par séance
- Plusieurs exercices par séance
- Correction automatique avec explications
- Score calculé automatiquement
- Sauvegarde des tentatives et progression

### 🎓 Examens Blancs
- Examens complets simulant les vrais examens
- Timer pour limiter le temps
- Questions issues de toutes les matières
- Statistiques de résultats
- Comparaison avec les autres utilisateurs

### 💳 Système d'Abonnement
- Paiement par Stripe
- Plusieurs formules d'abonnement (mensuel, annuel)
- Prix différents selon le statut (PASS/LASS/Terminale)
- Gestion automatique des renouvellements via webhooks

### 🎮 Gamification Basique
- **Points** : Gain de points en faisant des exercices
- **Streak** : Compteur de jours consécutifs de connexion
- **Badges** : Quelques badges basiques à débloquer
- **Classement** : Top des utilisateurs par points

### 🔔 Notifications
- Notifications in-app (non lues/lues)
- Paramètres de notification (activer/désactiver)

### 👤 Profil Utilisateur
- Modification des informations personnelles
- Changement de mot de passe
- Choix d'avatar parmi une sélection
- Gestion de l'abonnement

### 🛠️ Administration (Dashboard Admin)
- **Gestion des matières** : Créer, modifier, supprimer
- **Gestion des séances** : Créer, modifier, réorganiser, supprimer
- **Gestion des vidéos** : Ajouter/supprimer des vidéos par séance
- **Gestion des exercices** : Créer/modifier les QCM
- **Gestion des examens** : Créer/modifier les examens blancs
- **Gestion des utilisateurs** : Liste, modification, suppression
- **Gestion des offres** : Modifier les prix des abonnements
- **Envoi de notifications** : Notification globale à tous les users

### 📧 Emails Automatiques
- Email de bienvenue à l'inscription
- Email de réinitialisation de mot de passe

---

# 🚀 VERSION 2 - ÉVOLUTIONS SOUHAITÉES

## 1. Nouvelles Fonctionnalités Majeures

### 🤖 Intelligence Artificielle

#### Chat IA Conversationnel
- Interface de chat style ChatGPT
- L'étudiant peut poser des questions sur ses cours
- Réponses en streaming (temps réel)
- Historique des conversations sauvegardé
- Possibilité de créer plusieurs conversations

#### Upload et Analyse de Documents
- Upload de fichiers (PDF, Word, images)
- Extraction automatique du texte (OCR pour images)
- L'IA peut répondre en se basant sur les documents uploadés
- Résumé automatique des documents

#### Génération Automatique de Flashcards
- L'utilisateur uploade un document ou colle du texte
- L'IA génère automatiquement des flashcards (recto/verso)
- Choix du nombre de cartes et de la difficulté
- Possibilité de générer plus de cartes sur le même sujet

#### Génération Automatique de QCM
- À partir d'un texte ou document
- L'IA génère des questions à choix multiples
- Avec corrections et explications
- Choix du nombre de questions et difficulté

#### Génération de Fiches de Révision
- À partir des flashcards créées
- L'IA structure une fiche de révision complète
- Format éditable par l'utilisateur

#### Podcast IA (Text-to-Speech)
- Transformer un texte en podcast audio
- Voix naturelle (Azure Text-to-Speech)
- Téléchargeable en MP3

### 🎴 Système de Flashcards Complet

#### Organisation
- Catégories (ex: "UE1 - Biochimie")
- Sous-catégories (ex: "Chapitre 3 - Glucides")
- Couleurs et icônes personnalisables
- Épingler des catégories favorites

#### Création
- Création manuelle (recto/verso)
- Import depuis documents
- Génération par IA
- Ajout d'images sur les cartes

#### Révision
- Mode révision interactive
- Système de révision espacée (spaced repetition)
- Marquer comme "à revoir" ou "maîtrisé"
- Statistiques de révision

### 📝 QCM Personnel

#### Création de ses propres QCM
- Créer des catégories de QCM
- Ajouter des questions manuellement
- Ou générer par IA
- Définir les bonnes réponses et corrections

#### Entraînement
- S'entraîner sur ses propres QCM
- Historique des tentatives
- Statistiques de réussite

### 📅 Calendrier de Révisions Intelligent

#### Planification Automatique
- L'utilisateur crée une "matière" et des "chapitres"
- Définit une date de début pour chaque chapitre
- Le système génère automatiquement les dates de révision

#### Modèles de Révision Personnalisables
- Par défaut : J+1, J+3, J+7, J+14, J+30
- Possibilité de créer ses propres modèles
- Ex: "Mode intensif" : J+1, J+2, J+4, J+7

#### Interface Calendrier
- Vue mensuelle et hebdomadaire
- Drag & drop pour réorganiser
- Marquer les révisions comme faites
- Couleurs par matière

#### Rappels
- Notifications pour les révisions du jour
- Récapitulatif quotidien

### ⏱️ Timer Pomodoro Intégré

#### Fonctionnalités
- Timer configurable (25min focus, 5min pause, etc.)
- Cycles automatiques
- Mode "longue pause" après X sessions

#### Gamification
- Arbre virtuel qui pousse pendant le focus
- Feuilles et fruits à collecter
- Streak de jours consécutifs de pomodoro

#### Statistiques
- Temps total de focus par jour/semaine/mois
- Historique des sessions

### 🎮 Quiz Battle - Mode Multijoueur

#### Création de Partie
- Créer une "salle" avec un code
- Partager le code avec des amis
- Choisir la séance/matière du quiz

#### Gameplay Temps Réel
- Tous les joueurs répondent en même temps
- Classement en direct
- Points bonus pour la rapidité
- Chat pendant la partie

#### Résultats
- Podium final
- Statistiques de la partie
- Historique des parties

### 📊 Statistiques Avancées

#### Dashboard Personnel
- Temps d'étude par jour/semaine/mois
- Graphiques interactifs
- Progression par matière

#### Métriques Trackées
- Flashcards révisées
- QCM complétés
- Vidéos regardées
- Sessions pomodoro
- Score moyen aux exercices

#### Leaderboard Global
- Classement par XP
- Classement par niveau
- Filtres (cette semaine, ce mois, all-time)

### 🏆 Gamification Avancée

#### Système XP et Niveaux
- Gagner de l'XP pour chaque action
- Monter de niveau
- Affichage du niveau sur le profil

#### Badges Complets
- 30+ badges à débloquer
- Catégories : Streak, Quiz, Flashcards, Social, etc.
- Raretés : Commun, Rare, Épique, Légendaire
- Popup animé quand on débloque un badge
- Conditions de déblocage variées

#### Classements
- Classement global
- Classement par matière
- Classement hebdomadaire

### 🌍 Multi-Facultés

#### Personnalisation par Faculté
- L'utilisateur choisit sa faculté à l'inscription
- Les noms des séances peuvent varier selon la fac
- Certaines questions spécifiques par fac

#### Changement de Faculté
- Possibilité de changer (avec limite)

### 💰 Système de Crédits IA

#### Crédits
- Chaque génération IA consomme des crédits
- Crédits inclus dans l'abonnement
- Possibilité d'acheter des crédits supplémentaires

#### Historique
- Voir l'historique des dépenses de crédits
- Voir le solde restant

#### Parrainage
- Code de parrainage unique
- Gagner des crédits quand un filleul s'inscrit

### 📝 Éditeur de Notes Rich Text

#### Fonctionnalités
- Éditeur type Notion
- Formatage riche (titres, listes, gras, italique...)
- Insertion d'images
- Formules mathématiques (LaTeX)
- Sauvegarde automatique

#### Organisation
- Notes liées aux sous-catégories de flashcards
- Ou notes indépendantes

### 🔔 Système de Notifications Avancé (Admin)

#### Templates Email
- Créer des templates d'email personnalisés
- Variables dynamiques (nom, streak, etc.)
- Prévisualisation

#### Filtres Utilisateurs
- Créer des segments (ex: "inactifs depuis 7 jours")
- Filtrer par statut, abonnement, activité...

#### Campagnes
- Créer des campagnes email
- Planifier l'envoi
- Campagnes récurrentes (hebdomadaire, etc.)
- Statistiques (envoyés, ouverts, cliqués)

### 🐛 Reporting d'Erreurs Automatique

#### Côté Utilisateur
- Capture automatique des erreurs JavaScript
- Envoi au serveur avec contexte (page, navigateur, etc.)

#### Côté Admin
- Dashboard des erreurs
- Filtrer par sévérité, statut
- Marquer comme résolu
- Notes admin

### 📣 Bannières Promotionnelles (Admin)

#### Gestion
- Créer des bannières avec image
- Cibler : tous, gratuits uniquement, premium uniquement
- Activer/désactiver
- Réorganiser l'ordre d'affichage

### 📋 Enquête de Satisfaction (NPS)

#### Côté Utilisateur
- Popup d'enquête après X jours d'utilisation
- Score NPS (0-10)
- Questions ouvertes

#### Côté Admin
- Voir toutes les réponses
- Score NPS moyen
- Évolution dans le temps

### 🌐 Internationalisation

#### Langues Supportées
- Français (par défaut)
- Anglais
- (Extensible à d'autres langues)

#### Traduction
- Interface traduite
- Questions des QCM traduites
- Corrections traduites

### 🤖 Bot Telegram (Optionnel)

#### Fonctionnalités
- Recevoir les fiches publiés par les utilisateurs
- Leur choisir une matière et une séance et une faculté
- Création automatique de qcm ajoutés aux qcm de la séance sélectionné pour la faculté

### 🎨 UI/UX Moderne

#### Design
- Refonte complète du design
- Design system cohérent
- Composants modernes et accessibles
- Animations fluides

#### Thèmes
- Mode clair
- Mode sombre
- Préférence système

#### Mobile / Tablette
- Design responsive amélioré -> non fourni

---

# 📊 RÉSUMÉ DES ÉVOLUTIONS

## Tableau Comparatif

| Fonctionnalité | V1 | V2 |
|---------------|-----|-----|
| Auth basique | ✅ | ✅ |
| Cours vidéo | ✅ | ✅ |
| QCM séances | ✅ | ✅ Amélioré |
| Examens blancs | ✅ | ✅ |
| Paiement Stripe | ✅ (no webhook/synchronization) | ✅ Amélioré |
| Gamification | ❌ | Complète |
| **Chat IA** | ❌ | ✅ |
| **Flashcards** | ❌ | ✅ |
| **QCM Personnel** | ❌ | ✅ |
| **Calendrier Révisions** | ❌ | ✅ |
| **Pomodoro** | ❌ | ✅ |
| **Quiz Multijoueur** | ❌ | ✅ |
| **Stats Avancées** | ❌ | ✅ |
| **Multi-facultés** | ❌ | ✅ |
| **Crédits IA** | ❌ | ✅ |
| **Éditeur Notes** | ❌ | ✅ |
| **Notifs Marketing** | ❌ | ✅ |
| **Bug Reporting** | ❌ | ✅ |
| **i18n** | ❌ | ✅ |
| **Bot Telegram** | ❌ | ✅ |

---

# 📎 ANNEXES

## Accès Fournis sur Demande
- Accès à la V1 en production (lecture seule)
- Documentation technique de la V1
- Maquettes/Wireframes de la V2 (si disponibles)

## Contraintes Techniques
- Hébergement : VPS existant (possibilité d'upgrade)
- Budget API IA : illimité (optimisation demandé)
- Délai souhaité : 9 mois
