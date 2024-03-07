# ⚙️ Practica de App Engine

### Habilita la API de Google App Engine Admin <a href="#step4" id="step4"></a>

Recuerda primero debes ir al **Menú de navegación** (![Ícono del menú de navegación](https://cdn.qwiklabs.com/tkgw1TDgj4Q%2BYKQUW4jUFd0O5OEKlUMBRYbhlCrF0WY%3D)) de la consola de Cloud, haga clic en **APIs y servicios** > **Biblioteca**.

Haz clic en **Habilitar**.



Luego de esto abre la consola de google&#x20;

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

ahora vas a clonar el repo de prueba que nos dio Google para hacer esta practica

```bash
git clone https://github.com/GoogleCloudPlatform/python-docs-samples.git
```

Nos vamos a parar en la carpeta donde esta nuestro codigo&#x20;

```bash
cd python-docs-samples/appengine/standard_python3/hello_world
```

Dentro de esta carpeta existe un archivo `app.yaml`

De esta forma vamos a correr el codigo y ver lo funcionando.

```bash
dev_appserver.py app.yaml
```

Ahora ya que esta corriendo, lo podemos ver en la terminal de GCP vamos a darle click **Vista previa en la Web** (![Ícono de vista previa en la Web](https://cdn.qwiklabs.com/7b9oXblGsiFuNK7hmDZjFB%2B7Lrwdv5T64bbmo8X9FAo%3D)) > **Preview on port 8080**.

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-03 a la(s) 10.08.04 p.m..png" alt=""><figcaption></figcaption></figure>

Ahora debemos abrir una nueva ventana en la consola de GCP&#x20;

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

```bash
cd python-docs-samples/appengine/standard_python3/hello_world
```

```bash
nano main.py
```

y aqui puedes editar el codigo&#x20;

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-03 a la(s) 10.02.42 p.m..png" alt=""><figcaption></figcaption></figure>

y luego `Ctrl + S` y `Ctrl + C` y ya con eso puedes ir a mirar los cambios&#x20;



Deploy

```bash
gcloud app deploy
```

y para ver la direccion URL donde esta alojado

```bash
gcloud app browse
```

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-03 a la(s) 10.07.43 p.m..png" alt=""><figcaption></figcaption></figure>
