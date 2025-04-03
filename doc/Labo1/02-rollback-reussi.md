
# Étape 2 : Rollback du déploiement Nginx

## Objectif

Revenir à une version stable après une mise à jour cassée (image non valide), sans redéployer manuellement.

## Commande utilisée

```bash
kubectl rollout undo deployment nginx-deployment -n nginx-lab
