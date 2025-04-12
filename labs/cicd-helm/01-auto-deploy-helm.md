# 🚀 Labo 6 – Déploiement Helm automatisé via GitHub Actions

## 🎯 Objectif

Déclencher automatiquement le déploiement d’un chart Helm dans Kubernetes dès qu’un `git push` est effectué sur le dépôt GitHub.

---

## 🧱 Architecture

- ✅ GitHub Actions déclenche un workflow (`helm-auto-deploy.yml`)
- ✅ Ce workflow s'exécute sur un **runner auto-hébergé** installé sur la VM `k8s-master`
- ✅ Le chart Helm est stocké dans `nginx-custom-chart/`
- ✅ Le déploiement Helm est effectué dans le namespace `nginx-lab`

---

## 🧪 Étapes réalisées

### 1. 📦 Création d’un chart Helm

Chart généré avec :

```bash
helm create nginx-custom-chart
```

Contient :
- `Chart.yaml`
- `values.yaml`
- `templates/`

### 2. 💡 Ajout d’un workflow GitHub Actions `.github/workflows/helm-auto-deploy.yml`

Exécution automatique à chaque `push` sur `main` :

```yaml
runs-on: self-hosted
run: |
  cd nginx-custom-chart
  helm upgrade --install mon-nginx ./ --namespace nginx-lab --create-namespace
```

### 3. 🖥️ Configuration d’un runner auto-hébergé sur la VM `k8s-master`

- Téléchargement depuis GitHub
- Lancement avec `./run.sh`
- Runner détecte automatiquement les jobs

### 4. ✅ Vérification du déploiement

```bash
helm list -n nginx-lab
```

Sortie :

```
NAME        NAMESPACE   REVISION  UPDATED                                STATUS     CHART                    APP VERSION
mon-nginx   nginx-lab   2         2025-04-12 18:05:52 +0000 UTC          deployed   nginx-custom-chart-0.1.0 1.16.0
```

---

## 🧠 Ce qu’on a appris

- Utiliser un **runner auto-hébergé** dans un environnement privé
- Automatiser le déploiement Helm sans interaction manuelle
- Identifier les conditions où Helm **ne redéploie pas les pods** (si aucun changement)
- Séparer le workflow de **CI (kubeval)** du workflow de **CD (Helm)**

---

## ✅ Prochaine étape

➡️ Ajouter une validation de test ou un rollback automatique dans les futurs workflows CI/CD.