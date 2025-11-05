# 🌿 ComaLeaf - Plateforme de Détection de Maladies de Plantes

ComaLeaf est une application web complète développée avec Django qui permet de détecter automatiquement les maladies des plantes en analysant des images de feuilles. La plateforme inclut également un système de gestion de contenu pour les plantes, un forum communautaire, et un tableau de bord administrateur.

## ✨ Fonctionnalités Principales

### 🔬 Détection de Maladies de Plantes (IA)
- **Analyse d'images** : Upload de photos de feuilles pour détecter automatiquement les maladies
- **38 catégories** : Détection de maladies sur pommes, tomates, maïs, raisins, et bien d'autres plantes
- **Précision élevée** : Utilise un modèle TensorFlow/Keras entraîné pour une précision optimale
- **Détection de bords** : Visualisation automatique des zones affectées sur les feuilles
- **Classification** : Identification des maladies telles que :
  - Feu bactérien
  - Mildiou
  - Oïdium
  - Tache septorienne
  - Virus de la mosaïque
  - Et bien d'autres...

### 🌱 Gestion de Catalogue de Plantes
- **Base de données** : Catalogue complet de plantes avec photos et descriptions
- **Informations détaillées** : Nom scientifique, descriptions, images
- **Interface CRUD** : Ajout, modification, suppression de plantes (admin)
- **Navigation par catégories** : Parcours facile du catalogue

### 📝 Système de Publications Communautaire
- **Posts** : Création, édition et suppression de publications
- **Commentaires** : Interaction entre utilisateurs
- **Likes** : Système de j'aime pour les publications
- **Tags** : Catégorisation des posts par tags
- **Permissions** : Gestion des droits d'auteur et administrateur

### 👥 Gestion des Utilisateurs
- **Authentification** : Inscription et connexion
- **Profils personnalisés** : Photos de profil, informations utilisateur
- **Rôles** : Administrateurs, employés et utilisateurs standards
- **Tableau de bord** : Gestion des utilisateurs pour les admins

### 📧 Contact
- **Formulaire** : Envoi d'emails directement depuis l'application
- **Intégration SMTP** : Via Gmail

### 🎨 Interface Moderne
- **Tailwind CSS** : Design responsive et moderne
- **HTMX** : Interactions dynamiques sans rechargement de page
- **Widget Tweaks** : Amélioration des formulaires Django

## 🚀 Technologies Utilisées

### Backend
- **Django 5.2.4** : Framework web Python
- **TensorFlow/Keras** : Modèle d'apprentissage automatique
- **OpenCV** : Traitement d'images
- **NumPy** : Calculs numériques
- **Pillow** : Manipulation d'images
- **MySQL** : Base de données (avec support SQLite)

### Frontend
- **Tailwind CSS 4.1.11** : Framework CSS
- **HTMX** : Interactions web modernes
- **JavaScript** : Fonctionnalités interactives

### Outils
- **Widget Tweaks** : Amélioration des formulaires Django
- **Django HTMX** : Support HTMX pour Django

## 📋 Prérequis

- Python 3.8+
- MySQL Server (ou SQLite pour le développement)
- pip
- npm (pour Tailwind CSS)

## 🛠️ Installation

### 1. Cloner le dépôt
```bash
git clone https://github.com/votre-username/ComaPrimApp.git
cd ComaPrimApp
```

### 2. Créer un environnement virtuel
```bash
python -m venv venv
```

### 3. Activer l'environnement virtuel

**Windows:**
```bash
venv\Scripts\activate
```

**Linux/Mac:**
```bash
source venv/bin/activate
```

### 4. Installer les dépendances Python
```bash
pip install -r requirements.txt
```

### 5. Configurer la base de données

Éditez `comaLeaf/settings.py` pour configurer votre base de données MySQL :

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'comaleaf',
        'USER': 'votre_utilisateur',
        'PASSWORD': 'votre_mot_de_passe',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### 6. Créer la base de données
```bash
# Dans MySQL
CREATE DATABASE comaleaf CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

### 7. Appliquer les migrations
```bash
python manage.py makemigrations
python manage.py migrate
```

### 8. Créer un superutilisateur
```bash
python manage.py createsuperuser
```

### 9. Installer les dépendances frontend
```bash
npm install
```

### 10. Lancer le serveur de développement
```bash
python manage.py runserver
```

L'application sera accessible sur `http://localhost:8000`

## 📁 Structure du Projet

```
ComaPrimApp/
├── admin_dashboard/        # Tableau de bord administrateur
├── auth_app/               # Authentification et gestion utilisateurs
├── comaLeaf/              # Configuration principale Django
├── contact/               # Module de contact
├── core/                  # Vues principales (home, détection IA)
├── media/                 # Fichiers téléchargés (images)
├── model/                 # Modèle TensorFlow de détection
├── plants/                # Gestion du catalogue de plantes
├── publications/          # Système de posts communautaires
├── static/               # Fichiers statiques (CSS, JS)
└── manage.py             # Point d'entrée Django
```

## 🔐 Configuration de l'Email (Optionnel)

Pour activer l'envoi d'emails, éditez `comaLeaf/settings.py` :

```python
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST = 'smtp.gmail.com'
EMAIL_PORT = '587'
EMAIL_USE_TLS = True
EMAIL_HOST_USER = 'votre_email@gmail.com'
EMAIL_HOST_PASSWORD = 'votre_mot_de_passe_application'
```

## 🤖 Modèle de Détection

Le modèle IA `plant_model_v5-beta.h5` est un modèle TensorFlow/Keras pré-entraîné capable de détecter 38 catégories de maladies de plantes différentes. Il analyse les images de feuilles et fournit :
- Le nom de la maladie
- Le niveau de confiance
- La visualisation des zones affectées

## 📸 Catégories de Détection

- **Pommier** : Gale, pourriture noire, rouille, sain
- **Tomate** : Feu bactérien, mildiou précoce/tardif, moisissure foliaire, tache septorienne, acariens, virus
- **Maïs** : Tache grise cercosporienne, rouille, flétrissure septorienne, sain
- **Raisin** : Pourriture noire, esca, brûlure foliaire, sain
- **Piment** : Feu bactérien, sain
- **Autres** : Pomme de terre, pêche, cerise, fraise, etc.

## 🌐 URLs Principales

- `/` : Page d'accueil
- `/auth/connexion/` : Connexion
- `/auth/inscription/` : Inscription
- `/detection/` : Détection de maladies
- `/posts/` : Publications communautaires
- `/explore_plantes/` : Catalogue des plantes
- `/admin-dashboard/` : Tableau de bord admin
- `/contact/` : Formulaire de contact
- `/admin/` : Interface Django admin

## 🧪 Tests

Pour exécuter les tests :
```bash
python manage.py test
```

## 📝 License

Ce projet est sous licence MIT.

## 👨‍💻 Auteur

Développé avec ❤️ pour aider les agriculteurs et jardiniers à protéger leurs cultures.

## 🙏 Remerciements

- Dataset des maladies de feuilles
- Community Django pour l'excellent framework
- TensorFlow pour les outils d'IA

## 🐛 Rapport de Bugs

Si vous trouvez un bug, veuillez ouvrir une issue sur GitHub avec :
- La description du problème
- Les étapes pour reproduire
- Votre configuration (OS, version Python, Django)

## 🔮 Améliorations Futures

- [ ] Support multilingue
- [ ] API REST pour les applications mobiles
- [ ] Détection en temps réel via caméra
- [ ] Recommandations de traitement personnalisées
- [ ] Notifications push
- [ ] Système de points et badges
- [ ] Export de rapports PDF


-------------------------------------------------------------------------------
## 📧 Contact

Pour toute question, contactez :imanenouam7@gmail.com
---



