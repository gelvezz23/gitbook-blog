# Practica - Kubernetes

**Configura la región de procesamiento predeterminada**

```bash
gcloud config set compute/region us-east4
```

**Configura la zona de procesamiento predeterminada**

```bash
gcloud config set compute/zone us-east4-a
```

### Crea un clúster de GKE <a href="#step5" id="step5"></a>

```bash
gcloud container clusters create --machine-type=e2-medium --zone=us-east4-a lab-cluster 
```

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-10 a la(s) 6.17.26 p.m..png" alt=""><figcaption></figcaption></figure>

### Obtén las credenciales de autenticación para el clúster <a href="#step6" id="step6"></a>

```bash
gcloud container clusters get-credentials lab-cluster 
```

### Implementa una aplicación en el clúster <a href="#step7" id="step7"></a>

```bash
kubectl create deployment hello-server --image=gcr.io/google-samples/hello-app:1.0
```

Para **crear un objeto Service**, que es un recurso de Kubernetes que te permite exponer tu aplicación al tráfico externo, ejecuta el siguiente comando [kubectl expose](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#expose):

```bash
kubectl expose deployment hello-server --type=LoadBalancer --port 8080
```

Para **inspeccionar** el objeto Service `hello-server`, ejecuta [kubectl get](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#get):

```bash
kubectl get service
```

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-10 a la(s) 6.26.27 p.m..png" alt=""><figcaption></figcaption></figure>

ver corriendo&#x20;

```bash
http://[EXTERNAL-IP]:8080
```

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-10 a la(s) 6.26.47 p.m..png" alt=""><figcaption></figcaption></figure>

### Borra el clúster <a href="#step8" id="step8"></a>

```bash
gcloud container clusters delete lab-cluster 
```

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-10 a la(s) 6.33.54 p.m. (1).png" alt=""><figcaption></figcaption></figure>
