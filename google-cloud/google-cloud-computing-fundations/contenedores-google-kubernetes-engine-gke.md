---
description: Google Kubernetes Engine
---

# 🚌 Contenedores - Google Kubernetes Engine (GKE)

Organiza tus Apps con GKE, esto es un hibrido entre [**Iaas**](iaas-paas-saas.md) y [**Paas**](iaas-paas-saas.md), ofrece la administracion de Iaas con la horientacion de solo desarrollo de Paas

Con IaaS es posible compartir recursos con otros desarrolladores por medio de una maquina virtual [**VM**](crear-un-maquina-virtual-con-gcp.md)

**En este punto entran los contenedores** para brindar la escalabilidad del trabajo y asi dar un adstraccion del sistema operativo y el hardware necesario&#x20;



Pero ten en cuenta que esto tiene un costo&#x20;

La unidad de procesamiento mas peque;a es una app con su maquina virtual&#x20;



Un contenedor es una caja invisible que encapsula tu codigo con acceso limitado a esa particion en terminos mas simples el Sistema operatico esta virtualizado con sus herramientas dentro y lo podes hacer desde el local a la nube sin tener que cambiar nada&#x20;



Cuando usamos una arquitectura de microservicios se tiende a usar muchos contenedores&#x20;

<figure><img src="../../.gitbook/assets/Captura de pantalla 2023-05-10 a la(s) 6.03.40 p.m..png" alt=""><figcaption></figcaption></figure>

Kubernetes te organiza todos esos contenedores. Puedes instalar Kubernetes en un grupo de tus servidores administrados o ejecutarlo como servicio alojado en Google Cloud en un clúster de instancias administradas de Compute Engine

