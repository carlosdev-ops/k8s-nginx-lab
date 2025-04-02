
# Étape 5 : Rolling update du déploiement Nginx

## Objectif

Mettre à jour l’image Docker de `nginx` de la version `1.25` à `1.26`, sans interruption de service.

## Modification du fichier `nginx-deployment.yaml`

```diff
- image: nginx:1.25
+ image: nginx:1.26
