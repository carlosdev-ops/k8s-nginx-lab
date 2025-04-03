
# Étape 3 : Déploiement d’un objet Deployment Nginx

## Fichier `nginx-deployment.yaml`

```yaml
apiVersion: apps/v1          # Version de l’API utilisée pour un Deployment
kind: Deployment             # Type de ressource : Deployment
metadata:
  name: nginx-deployment     # Nom du déploiement
  namespace: nginx-lab       # Namespace cible
spec:
  replicas: 3                # Nombre de pods souhaités
  selector:
    matchLabels:
      app: nginx             # Permet d’associer les pods à ce deployment
  template:                  # Gabarit utilisé pour créer les pods
    metadata:
      labels:
        app: nginx           # Label utilisé pour identifier les pods
    spec:
      containers:
        - name: nginx        # Nom du conteneur dans le pod
          image: nginx:1.25  # Image Docker à utiliser
          ports:
            - containerPort: 80  # Port exposé dans le conteneur
