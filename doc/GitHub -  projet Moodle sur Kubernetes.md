# 📘 Moodle sur Kubernetes 


---

## 🗂️ Structure du dépôt GitHub

```bash
moodle-k8s-infra/
├── infra/          # Scripts pour déployer le cluster
├── k8s/
│   ├── dev/        # Déploiement Moodle DEV
│   ├── stage/      # Déploiement Moodle STAGE
│   └── prod/       # Déploiement Moodle PROD
├── scripts/        # Automatisation Bash / Python
├── tests/          # Tests de panne / résilience
├── docs/           # Ajout des notes Obsidian dans le dossier docs
├── README.md       # Présentation du projet
└── .gitignore      # Fichiers à ignorer

