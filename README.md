# 📺 Anime Tracker

Un traqueur automatisé qui surveille votre compte **AniList** pour détecter instantanément la sortie ou l'annonce de nouvelles suites (*sequels*) de vos animés préférés. 

Le projet est conçu pour être développé en deux temps : une **Phase 1 (CLI)** robuste en arrière-plan, suivie d'une **Phase 2 (GUI)** élégante avec PySide6 (et apres serveur db, User).

---

## 🛠️ Structure du Projet

```text
anime-tracker/
│
├── main.py                     # Point d'entrée de l'application
├── config.py                   # Configuration centralisée (Constantes)
├── requirements.txt            # Dépendances du projet
├── .gitignore                  # Fichiers à exclure du versionnage
│
├── api/                        # Gestion des requêtes externes
│   ├── __init__.py
│   └── anilist.py              # Client API GraphQL AniList
│
├── core/                       # Logique métier
│   ├── __init__.py
│   ├── tracker.py              # Chef d'orchestre du cycle de vérification
│   └── detector.py             # Algorithme de détection des suites
│
├── db/                         # Persistance des données
│   ├── __init__.py
│   └── database.py             # Gestion de la base SQLite locale
│
├── notifications/              # Alertes utilisateur
│   ├── __init__.py
│   └── notifier.py             # Notifications OS natives
│
├── gui/                        # [Phase 2] Interface graphique
│   ├── __init__.py
│   ├── main_window.py          # Fenêtre principale Qt
│   ├── tray.py                 # Icône dans la barre des tâches
│   └── widgets.py              # Composants réutilisables & Threads
│
├── utils/                      # Outils transverses
│   ├── __init__.py
│   └── logger.py               # Système de logs rotatifs
│
├── resources/                  # Assets de l'application
│   └── icons/
│       └── app.ico
│
└── data/                       # Données locales (Généré automatiquement)
    ├── local.db                # Base de données SQLite
    └── tracker.log             # Fichier de logs
