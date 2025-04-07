# 🔧 Kubernetes NGINX Labs – by Carlos
![CI](https://github.com/carlosdev-ops/kube-lab-nginx/actions/workflows/kube-lint.yml/badge.svg)
![Ubuntu](https://img.shields.io/badge/Ubuntu-24.04-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)
![Proxmox](https://img.shields.io/badge/Proxmox-VE-orange?style=for-the-badge&logo=proxmox&logoColor=white)
![100% YAML](https://img.shields.io/badge/100%25-YAML-informational?style=for-the-badge&logo=yaml&logoColor=white)
![Helm Chart](https://img.shields.io/badge/Helm-✅-0f1689?style=for-the-badge&logo=helm&logoColor=white)


---

## 📘 À propos du projet

Ce dépôt présente une série de laboratoires Kubernetes conçus pour apprendre, pratiquer et maîtriser les concepts clés liés aux déploiements manuels, à l’automatisation CI/CD, et à Helm.

Chaque labo est documenté, validé, versionné et exécuté dans un environnement virtualisé via Proxmox, avec des VMs Ubuntu 24.04.

---

## 🚀 Récapitulatif des Labos terminés

| Labo | Titre                                | Description                                                                 |
|------|--------------------------------------|-----------------------------------------------------------------------------|
| ✅ 1 | Déploiement manuel d’un pod Nginx (YAML) | Fichiers YAML écrits à la main, exposés en NodePort                        |
| ✅ 2 | Ingress Controller avec NGINX        | Installation du NGINX Ingress Controller et test d’accès HTTP              |
| ✅ 3 | MySQL avec volumes persistants       | Déploiement avec PVC/PV (hostPath), nodeSelector et accès externe          |
| ✅ 4 | CI/CD avec GitHub Actions            | Validation automatique des fichiers YAML Kubernetes via kubeval            |
| ✅ 5 | Helm Chart personnalisé              | Création d’un chart Helm épuré, déploiement dynamique avec `values.yaml`   |

---

## 🔜 Prochaine étape

🎯 **Objectif Labo 6**  
Mettre en place un pipeline GitHub Actions qui :
- valide les charts Helm
- déploie automatiquement dans le cluster Kubernetes via `helm upgrade --install`

---

## 🧠 Technologies utilisées

- 🐧 Ubuntu 24.04
- 🧱 Kubernetes (kubeadm, YAML)
- 🔁 Helm 3
- 🚀 GitHub Actions
- 🧪 kubeval
- 📦 Proxmox (infrastructure locale)
- ✍️ Édition CLI : `vim`, `kubectl`, `helm`, `ks9`

---

## 📂 Structure du dépôt

kube-lab-nginx/ ├── labs/ │ ├── nginx/ │ ├── ingress/ │ ├── mysql/ │ ├── cicd/ │ └── helm/ ├── .github/ │ └── workflows/ └── README.md
