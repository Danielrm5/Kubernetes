# 1. Introducción a Kubernetes

Este apartado resume los conceptos fundamentales de **Kubernetes** (Módulo 1) y sirve como base para las prácticas del repositorio.

---

## 1. El problema real

En entornos actuales las aplicaciones deben cumplir cuatro requisitos clave:

- **Disponibilidad 24/7:** no pueden detenerse.
- **Muchos usuarios simultáneos:** requieren capacidad de respuesta y reparto de carga.
- **Cambios constantes:** actualizaciones frecuentes de código y configuración.
- **Cero paradas:** actualizar o recuperarse de fallos sin interrumpir el servicio.

---

## 2. Contenedores: primera solución

Un **contenedor** empaqueta una aplicación junto con todas sus dependencias para aislarla y garantizar que funcione igual en cualquier entorno.

Sin embargo, usar contenedores sueltos no es suficiente en producción porque:

- No escalan automáticamente según la demanda.
- No se recuperan por sí solos si un contenedor o servidor falla.
- No balancean la carga entre réplicas de forma automática.

---

## 3. ¿Qué es Kubernetes?

**Kubernetes (K8s)** es un **orquestador de contenedores** pensado para producción que automatiza la gestión de aplicaciones en múltiples servidores:

- Ejecuta contenedores automáticamente y decide en qué nodo colocarlos.
- Mantiene el número deseado de copias (réplicas).
- Escala según la carga.
- Se recupera automáticamente ante fallos.
- Permite actualizar aplicaciones sin detener el servicio.

---

## 4. Arquitectura de Kubernetes

Un **clúster** de Kubernetes es un conjunto de máquinas (**nodos**) que trabajan juntas y se dividen en dos roles:

- **Control Plane (Master):** es el cerebro del clúster; toma decisiones y mantiene el estado deseado (no ejecuta las aplicaciones de usuario). Sus componentes principales son:
  - **API Server (`kube-apiserver`):** punto de entrada al clúster (por ejemplo, donde se conecta `kubectl`).
  - **etcd:** base de datos que guarda el estado del clúster.
  - **Scheduler (`kube-scheduler`):** decide en qué *Worker Node* se ejecuta cada Pod.
  - **Controller Manager:** vigila que el estado actual coincida con el estado definido.
- **Worker Nodes:** son los nodos donde se ejecutan realmente las aplicaciones dentro de **Pods** (unidades mínimas de uno o varios contenedores):
  - **kubelet:** agente en cada nodo que recibe órdenes del *Control Plane* y verifica que los contenedores funcionen.
  - **Container Runtime (`containerd`):** componente encargado de arrancar, ejecutar y detener los contenedores.

---

## 5. Otros orquestadores

Existen otras herramientas de orquestación como **Docker Swarm** (integrado en Docker y más sencillo pero limitado), **Apache Mesos** o **HashiCorp Nomad**. Frente a ellas, **Kubernetes** se ha consolidado como el estándar de facto en producción por su escalado avanzado, alta disponibilidad y amplio ecosistema.

---

## Relación con los módulos prácticos del repositorio

- **[2. Instalación](../Instalacion/):** puesta en marcha de un clúster local con **Minikube** (usando VirtualBox y Docker) y el cliente **`kubectl`** para interactuar con la API del clúster.
- **[3. PODS](../PODS/):** creación, inspección, acceso interactivo, logs, redirección de puertos (`port-forward`) y uso de Pods multicontenedor con volúmenes compartidos.
- **[4. Replica sets](../replica%20sets/):** mantenimiento de un número estable de réplicas de un Pod.
- **[5. Deployments](../deployments/):** gestión declarativa de despliegues y actualizaciones sin parada de servicio.

---

[⬅️ Volver al índice](../README.md)
