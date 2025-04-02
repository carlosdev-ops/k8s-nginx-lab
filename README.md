![Kubernetes Lab](https://img.shields.io/badge/Kubernetes_Lab-validé-brightgreen?style=for-the-badge&logo=kubernetes&logoColor=white)
![Pop!_OS](https://img.shields.io/badge/Pop!_OS-22.04-blue?style=for-the-badge&logo=system76&logoColor=white)
![Proxmox](https://img.shields.io/badge/Proxmox-VE-orange?style=for-the-badge&logo=proxmox&logoColor=white)
![100% YAML](https://img.shields.io/badge/100%25-YAML-informational?style=for-the-badge&logo=yaml&logoColor=white)

# Kubernetes Nginx Lab

Ce projet est un laboratoire d’apprentissage progressif sur Kubernetes, réalisé dans un cluster Proxmox avec 1 master et 2 workers.

## 🎯 Objectifs

- Créer un namespace dédié (`nginx-lab`)
- Déployer un pod Nginx simple
- Passer à un Deployment avec 3 pods
- Exposer le service avec NodePort
- Tester une mise à jour sans interruption (rolling update)
- Documenter chaque étape avec des fichiers Markdown
- Versionner le tout dans un dépôt GitHub

## 🏗️ Structure du projet

```bash
.
├── doc/
│   ├── 01-namespace.md
│   ├── 02-pod-nginx.md
│   ├── 03-deployment-nginx.md
│   ├── 04-service-nodeport.md
│   ├── 05-rolling-update.md
│   └── ...
├── yaml/
│   ├── nginx-deployment.yaml
│   ├── nginx-pod.yaml
│   └── nginx-service.yaml
└── README.md

