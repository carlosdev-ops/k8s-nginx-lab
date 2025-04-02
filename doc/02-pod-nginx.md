# Étape 2 : Déploiement d’un Pod Nginx

Création du fichier `nginx-pod.yaml` :

```yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  namespace: nginx-lab
spec:
  containers:
    - name: nginx
      image: nginx:1.25
      ports:
        - containerPort: 80

