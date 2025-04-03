
# Étape 6 : Rollback du déploiement Nginx

## Objectif

Annuler la mise à jour et revenir à la version précédente de l’image Nginx.

## Commande utilisée

```bash
kubectl rollout undo deployment nginx-deployment -n nginx-lab
