
# Labo 1 : Rollback d’un déploiement Kubernetes

## Objectif

Simuler une mise à jour cassée (image non valide), puis revenir à la version précédente avec `kubectl rollout undo`.

## Étapes

1. Modification du fichier :

```yaml
image: nginx:doesnotexist
