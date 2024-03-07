# ⚙️ Practica Cloud Functions

En la consola de comandos de GCP vamos a crear una carpeta con la funcion&#x20;

```bash
mkdir gcf_hello_world
```

```bash
cd gcf_hello_world
```

vamos a crear un archivo JS&#x20;

```bash
nano index.js
```

dentro vamos a meter el siguiente codigo&#x20;

```javascript
/**
* Background Cloud Function to be triggered by Pub/Sub.
* This function is exported by index.js, and executed when
* the trigger topic receives a message.
*
* @param {object} data The event payload.
* @param {object} context The event metadata.
*/
exports.helloWorld = (data, context) => {
const pubSubMessage = data;
const name = pubSubMessage.data
    ? Buffer.from(pubSubMessage.data, 'base64').toString() : "Hello World";
console.log(`My Cloud Function: ${name}`);
};
```

Sal de nano (Ctrl + x) y guarda (Y) el archivo.

Creamos el Bucket en Cloud Storage

```bash
gsutil mb -p [PROJECT_ID] gs://[BUCKET_NAME]
```

para el nombre de bucket puede leer esta documentacion&#x20;

{% embed url="https://cloud.google.com/storage/docs/buckets#naming" %}

Para el **\[PROJECT\_ID]** puedes usar el siguiente comando&#x20;

```bash
gcloud config list project
```



Ahora vamos a implementar el codigo&#x20;

```bash
gcloud functions deploy helloWorld --stage-bucket [BUCKET_NAME] --trigger-topic hello_world --runtime nodejs8
```

verificamos el estado&#x20;

```bash
gcloud functions describe helloWorld
```

La probamos&#x20;

```bash
DATA=$(printf 'Hello World!'|base64) && gcloud functions call helloWorld --data '{"data":"'$DATA'"}'
```

ver los registros&#x20;

```bash
gcloud functions logs read helloWorld
```

