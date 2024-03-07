# ⌨️ Crear un Maquina Virtual con GCP

Primero vamos a ir a la consola de Google cloud \


una vez ahi dentro \


<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

se te abrira una terminal para poder escribir

vas a escribir el siguiente comando para ver el nombre de la cuenta activa&#x20;

```batch
gcloud auth list
```

Mostrar el ID de proyecto

```bash
gcloud config list project
```

### Cree una nueva instancia desde la consola de Cloud <a href="#step4" id="step4"></a>

**Menú de navegación** (![Ícono del menú de navegación](https://cdn.qwiklabs.com/tkgw1TDgj4Q%2BYKQUW4jUFd0O5OEKlUMBRYbhlCrF0WY%3D)) de la consola de Cloud, haga clic en **Compute Engine** > **Instancias de VM**.



aqui vamos a escoger lo que necesitamos para crear  nuestra maquina virtual

Te va a pedir unas espesificaciones y pues esta parte tu vas a configurar la maquina virtual con los recursos que necesites&#x20;

Luedo de dar le en el boton **crear** le puedes dar click en el boton de **SSH** y con esto ya estarias en la consola por conexion **SSH** en tu maquina virtual



### Instale un servidor web de NGINX <a href="#step5" id="step5"></a>



Instalar NGINX&#x20;

```bash
 sudo apt-get install -y nginx
```

confirmar su ejecucion&#x20;

```bash
 ps auwx | grep nginx
```

Y ya podras ver en la IP externa de tu maquina virtual el contenido \
\
