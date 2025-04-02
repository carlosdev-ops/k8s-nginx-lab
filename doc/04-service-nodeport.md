

# Étape 4 : Exposer Nginx via un Service NodePort

## Fichier `nginx-service.yaml`

```yaml
apiVersion: v1                # API pour les services
kind: Service                 # Ressource de type Service
metadata:
  name: nginx-service         # Nom du service
  namespace: nginx-lab        # Namespace utilisé
spec:
  selector:
    app: nginx                # Sélectionne les pods avec le label "app: nginx"
  type: NodePort              # Type d’exposition externe (port d’un node)
  ports:
    - port: 80                # Port du service
      targetPort: 80          # Port du conteneur dans les pods
      nodePort: 30080         # Port d’accès externe (dans la plage 30000-32767)
