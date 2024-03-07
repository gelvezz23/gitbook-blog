# Cloud Run

Es un servicio de contenedores administrado, es una tecnologia sin servidores eso quiere decir que quita las tareas de administracion de infraestructura



usa Knative una herramienta de Kubernetes y se te cobra por 100 milisegundos asi que no pagaras por un aprovisionamiento excesivo de recursos&#x20;

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-10 a la(s) 6.46.03 p.m..png" alt=""><figcaption></figcaption></figure>

1. escribe una aplicacion en el codigo que mas te guste&#x20;
2. empaqueta tu aplicacion en un contenedor
3. implementar la imagen de un contenedor en cloud run

El flujo de trabajo con contenedores nos permite flexibilidad y escalabilidad&#x20;

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-10 a la(s) 6.50.17 p.m..png" alt=""><figcaption></figcaption></figure>



cloud run encripta los paquetes que llegan de tal forma que tu solo debes preocuparte de la informacion a procesar de esta forma esta expuesta tu aplicacion a un subdominio único del dominio **\*run.app global**

**Tambien te genera el certificado SSL valido**&#x20;



**El cobro de este serivicio es unico ya que solo pagas por los recursos que vas a usar, cuando estas iniciando o apagando no vas a pagar si tu contenedor no tiene nada ni resive solicitudes**&#x20;

Por pasar del millon el solicitudes resives un descuento&#x20;

Un contenedor con más CPU virtual y memoria es más costoso



