## Chart YAML

Le fichier `values.yaml` définit les paramètres injectables dans les templates Helm.


# 🧪 Labo 5 – Helm Chart personnalisé pour Nginx

Ce labo montre comment créer un chart Helm personnalisé pour déployer un serveur Nginx dans un cluster Kubernetes.

---

## 🎯 Objectif

- Créer un chart Helm propre et minimaliste
- Déployer Nginx avec des valeurs dynamiques via `values.yaml`
- Exposer le service via NodePort pour un accès depuis un navigateur

---

## 🧱 Étapes détaillées

### 1. Créer le chart

```bash
helm create nginx-custom-chart

### 2. Nettoyer les fichiers inutiles

bash

CopyEdit

`cd nginx-custom-chart/templates rm ingress.yaml hpa.yaml serviceaccount.yaml tests/test-connection.yaml rm ../templates/NOTES.txt`

---

### 3. Modifier `values.yaml`

yaml

CopyEdit

`replicaCount: 2  image:   repository: nginx   tag: stable   pullPolicy: IfNotPresent  service:   type: NodePort   port: 80   nodePort: 30081  resources: {} nodeSelector: {} tolerations: [] affinity: {}`

---

### 4. Modifier `templates/deployment.yaml`

yaml

CopyEdit

`apiVersion: apps/v1 kind: Deployment metadata:   name: nginx   labels:     app: nginx spec:   replicas: {{ .Values.replicaCount }}   selector:     matchLabels:       app: nginx   template:     metadata:       labels:         app: nginx     spec:       containers:         - name: nginx           image: "{{ .Values.image.repository }}:{{ .Values.image.tag }}"           imagePullPolicy: {{ .Values.image.pullPolicy }}           ports:             - containerPort: 80`

---

### 5. Créer `templates/service.yaml`

yaml

CopyEdit

`apiVersion: v1 kind: Service metadata:   name: nginx   labels:     app: nginx spec:   type: {{ .Values.service.type }}   selector:     app: nginx   ports:     - port: {{ .Values.service.port }}       targetPort: 80       nodePort: {{ .Values.service.nodePort }}`

---

### 6. Vérification du chart

bash

CopyEdit

`helm lint .`

---

### 7. Déploiement

bash

CopyEdit

`helm install mon-nginx ./ --namespace nginx-lab --create-namespace`

---

### 8. Accès dans le navigateur

Depuis votre poste local :  
http://10.0.0.143:30081