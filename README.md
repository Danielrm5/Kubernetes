<div align="center">

# ☸️ Curso de Kubernetes

![Kubernetes](https://img.shields.io/badge/Kubernetes-v1.37-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white)
![Minikube](https://img.shields.io/badge/Minikube-v1.39-F7931E?style=for-the-badge&logo=kubernetes&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Containerd-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![License](https://img.shields.io/badge/Licencia-GPL--3.0-green?style=for-the-badge)

Repositorio de apuntes, manifiestos YAML y prácticas documentadas paso a paso sobre administración y orquestación de contenedores con **Kubernetes**.

**Autor:** Daniel Romero (`Danielrm5`)

</div>

---

## 📑 Índice del Repositorio

| Módulo | Apartado | Contenido principal | Estado |
| :---: | :--- | :--- | :---: |
| **1** | **[📘 1. Introducción](./Introduccion/)** | Conceptos base, contenedores vs. orquestación y arquitectura del clúster (*Control Plane* y *Worker Nodes*). | ✅ Completado |
| **2** | **[⚙️ 2. Instalación](./Instalacion/)** | Instalación paso a paso de **Minikube** y **kubectl**, pruebas con VirtualBox y configuración final con **Docker**. | ✅ 17 capturas |
| **3** | **[📦 3. PODS](./PODS/)** | Creación imperativa/declarativa, inspección, logs, `port-forward` y Pods multicontenedor con volúmenes.<br>↳ [Tarea 3.2: Trabajando con Pods](./PODS/mODULO3/tarea3.2.%20Trabajando%20con%20PODS/)<br>↳ [Tarea 3.3: Pod multicontenedor](./PODS/mODULO3/tarea3.3.-Trabajando%20con%20un%20POD%20multicontenedor/) | ✅ 18 capturas |
| **4** | **[🔁 4. Replica sets](./replica%20sets/)** | Alta disponibilidad, auto-recuperación y mantenimiento de réplicas con `ReplicaSet` (`modulo4`). | 🔄 En curso |
| **5** | **[🚀 5. Deployments](./deployments/)** | Gestión declarativa de despliegues, escalado y actualizaciones sin parada (*Rolling Updates*). | 📌 Próximamente |

---

## 🛠️ Comandos Rápidos de Referencia

| Acción | Comando |
| :--- | :--- |
| Iniciar / detener el clúster local | `minikube start` / `minikube stop` |
| Ver estado de los nodos | `kubectl get nodes -o wide` |
| Aplicar un manifiesto YAML | `kubectl apply -f archivo.yaml` |
| Listar todos los recursos | `kubectl get all` |
| Inspeccionar un Pod en detalle | `kubectl describe pod/<nombre-pod>` |
| Abrir consola interactiva en un Pod | `kubectl exec -it pod/<nombre-pod> -- /bin/bash` |
| Redirigir un puerto local al Pod | `kubectl port-forward pod/<nombre-pod> 8088:80` |
| Consultar los logs de un Pod | `kubectl logs pod/<nombre-pod>` |
